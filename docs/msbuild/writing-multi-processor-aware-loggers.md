---
title: Více-procesorů protokolovacích nástrojů pro zápis | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, multi-proc aware loggers
- multi-proc loggers
- loggers, multi-proc
ms.assetid: ff987d1b-1798-4803-9ef6-cc8fcc263516
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a01fb5d47f390c311f119e669e7fdb75619b058
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31572592"
---
# <a name="writing-multi-processor-aware-loggers"></a>Zápis protokolovacích nástrojů pro více procesorů
Schopnost [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] chcete využít výhod více procesorů, může snížit čas sestavení projektu, ale také přidá složitost tak, aby sestavení protokolování událostí. V prostředí s jedním procesorem událostí, zprávy, upozornění a chyby přicházejí na protokolovacího nástroje předvídatelný, sekvenční způsobem. V prostředí s více procesory, můžete však události z různých zdrojů dorazí, ve stejnou dobu nebo mimo pořadí. Zajistit pro to, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje více-procesorů podporující protokolovacího nástroje a nový model protokolování a umožňuje vám vytvořit vlastní "předávání protokolovacích nástrojů."  
  
## <a name="multi-processor-logging-challenges"></a>Výzvy protokolování pro více procesorů  
 Při sestavování jednoho nebo více projektů v systému více procesorů nebo více jader, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] události sestavení pro všechny projekty jsou generovány ve stejnou dobu. Lavině zprávy o událostech může přicházejí na protokolovacího nástroje ve stejnou dobu nebo mimo pořadí. Protože [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0 protokolovač nebyla navržena pro zpracování této situace, může způsobit časy vyšší sestavení, výstup nesprávný protokolovacího nástroje nebo dokonce poškozená sestavení a zahlcovat protokolovacího nástroje. Chcete-li vyřešit tyto problémy, protokolovacího nástroje (počínaje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5) můžete zpracovat události mimo pořadí a korelovat události a jejich zdroje.  
  
 Efektivitu protokolování lze ještě více zlepšit vytvořením vlastního předávajícího protokolovacího nástroje. Protokolovač vlastní předávání funguje jako filtr umožňuje tím, než vytvoříte, vyberte jenom události, kterou chcete sledovat. Pokud používáte vlastní předávání protokolovač, nelze nežádoucí události zahlcovat protokolovacího nástroje, zbytečných souborů protokolů služby nebo pomalu sestavení časy.  
  
## <a name="multi-processor-logging-models"></a>Modely protokolování pro více procesorů  
 Zajistit pro problémy vázanými na více procesorů sestavení [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podporuje dva modely protokolování centrální a distribuované.  
  
### <a name="central-logging-model"></a>Model centrálního protokolování  
 V modelu s centrální protokolování jednu instanci MSBuild.exe funguje jako "centrální uzel" a podřízené instance centrálního uzlu (dále jen "sekundární uzly") připojení k centrální uzlu pomáhají provádět úlohy sestavení.  
  
 ![Model centrálního protokolovacího nástroje](../msbuild/media/centralnode.png "CentralNode")  
  
 Protokolovací nástroje různých typů, které připojit k centrálního uzlu se označují jako "centrální protokolovačů." Jenom jednu instanci každého typu protokolovacího nástroje lze připojit k uzlu centrální ve stejnou dobu.  
  
 Když dojde k sestavení, sekundární uzly směrovat jejich událostí sestavení do centrálního uzlu. Uzlu centrální směruje na jeden nebo více připojené centrální protokolovačů všechny jeho události a také u sekundární uzly. Protokolovacích nástrojů pak vytvořte soubory protokolů, které jsou založené na příchozí data.  
  
 I když pouze <xref:Microsoft.Build.Framework.ILogger> je potřeba k implementaci pomocí centrální protokolovacího nástroje, doporučujeme, aby taky implementovat <xref:Microsoft.Build.Framework.INodeLogger> tak, aby centrální protokolovacího nástroje inicializuje počet uzlů, které se účastní sestavení. Toto přetížení z <xref:Microsoft.Build.Framework.ILogger.Initialize%2A> metoda vyvolá, když modul inicializuje protokolovacího nástroje.  
  
```csharp
public interface INodeLogger: ILogger  
{  
    public void Initialize(IEventSource eventSource, int nodeCount);  
}  
```  
  
 Všechny existující <xref:Microsoft.Build.Framework.ILogger>– na základě protokolovacích nástrojů může fungovat jako centrální protokolovacích nástrojů a můžete připojit k sestavení. Centrální protokolovacích nástrojů zapsána bez explicitního podpory pro scénáře protokolování pro více procesorů a události na více systémů pořadí však může přerušit sestavení nebo vytvoření smysl výstupu.  
  
### <a name="distributed-logging-model"></a>Model distribuovaného protokolování  
 V modelu s centrální protokolování příliš mnoho příchozí provoz zprávu můžete zahlcovat centrálního uzlu, například při sestavení mnoha projektů ve stejnou dobu. To můžete vystavila zátěži systémové prostředky a snížit výkon sestavení. K usnadnění tyto potíže odstranit, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podporuje model distribuované protokolování.  
  
 ![Distribuované protokolování modelu](../msbuild/media/distnode.png "DistNode")  
  
 Model distribuované protokolování rozšiřuje model Centrální protokolování umožňují vytvářet předávání protokolovacího nástroje.  
  
#### <a name="forwarding-loggers"></a>Předávání protokolovacích nástrojů  
 Protokolovač přesměrování je sekundární, lightweight protokolovacího nástroje, který má filtr událostí, která připojí k sekundární uzel a přijímá příchozí událostí sestavení z daného uzlu. Ho filtry příchozí události a předá pouze ty, které zadáte do centrálního uzlu. Tím se snižuje přenos zpráv, který je odeslán do uzlu centrální a zlepšuje celkový výkon sestavení.  
  
 Existují dva způsoby, jak použít distribuované protokolování, následujícím způsobem:  
  
-   Přizpůsobení protokolovacího nástroje předem kovodělných předávání s názvem <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger>.  
  
-   Zápis vlastní vlastní předávání protokolovacího nástroje.  
  
 Můžete upravit ConfigurableForwardingLogger podle svých potřeb. K tomuto účelu volání protokolovacího nástroje na příkazovém řádku s použitím MSBuild.exe a seznam událostí sestavení, které chcete protokolovacího nástroje předávání do centrálního uzlu.  
  
 Alternativně můžete vytvořit vlastní předávání protokolovače. Vytvořením vlastní předávání protokoly můžete doladit tak chování protokolovacího nástroje. Vytváření protokolovacího nástroje vlastní přesměrování je však mnohem složitější než právě přizpůsobení ConfigurableForwardingLogger. Další informace najdete v tématu [vytváření předávání protokolovacích nástrojů](../msbuild/creating-forwarding-loggers.md).  
  
## <a name="using-the-configurableforwardinglogger-for-simple-distributed-logging"></a>Pomocí ConfigurableForwardingLogger pro jednoduché distribuované protokolování  
 Připojit ConfigurableForwardingLogger nebo vlastní předávání protokoly, použijte `/distributedlogger` přepínače (`/dl` pro zkrácení) v sestavení příkazového řádku MSBuild.exe. Formát pro zadání názvy typů protokolovacího nástroje a třídy je stejný jako pro `/logger` přepnout, s tím rozdílem, že distribuované protokolovacího nástroje má vždy dvě třídy protokolování místo jeden protokolovacího nástroje předávání a centrální protokolovacího nástroje. Následuje příklad toho, jak připojit vlastní předávání protokolovač, s názvem XMLForwardingLogger.  
  
```  
msbuild.exe myproj.proj/distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,Culture=neutral*XMLForwardingLogger,MyLogger,Version=1.0.2,Culture=neutral  
```  
  
> [!NOTE]
>  Znak hvězdičky (*) musí oddělte názvy dvou protokolovacího nástroje v `/dl` přepínače.  
  
 Použití ConfigurableForwardingLogger se podobá pomocí jiné protokoly (jak je uvedeno v [získání sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md)), s tím rozdílem, že připojení protokolovacího nástroje ConfigurableForwardingLogger místo typické [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] protokolovacího nástroje a zadejte jako parametry události, které chcete ConfigurableForwardingLogger předat centrálního uzlu.  
  
 Například pokud chcete být upozorněni jenom v případě, že je sestavení spustí a končí, a pokud dojde k chybě, předat `BUILDSTARTEDEVENT`, `BUILDFINISHEDEVENT`, a `ERROREVENT` jako parametry. Několik parametrů lze předat jejich oddělením středníkem. Následuje příklad použití ConfigurableForwardingLogger předávat jenom `BUILDSTARTEDEVENT`, `BUILDFINISHEDEVENT`, a `ERROREVENT` události.  
  
```  
msbuild.exe myproj.proj /distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,Culture=neutral*ConfigureableForwardingLogger,C:\My.dll;BUILDSTARTEDEVENT; BUILDFINISHEDEVENT;ERROREVENT  
```  
  
 Následuje seznam dostupných parametrů ConfigurableForwardingLogger.  
  
|Parametry ConfigurableForwardingLogger|  
|---------------------------------------------|  
|BUILDSTARTEDEVENT|  
|BUILDFINISHEDEVENT|  
|PROJECTSTARTEDEVENT|  
|PROJECTFINISHEDEVENT|  
|TARGETSTARTEDEVENT|  
|TARGETFINISHEDEVENT|  
|TASKSTARTEDEVENT|  
|TASKFINISHEDEVENT|  
|ERROREVENT|  
|WARNINGEVENT|  
|HIGHMESSAGEEVENT|  
|NORMALMESSAGEEVENT|  
|LOWMESSAGEEVENT|  
|CUSTOMEVENT|  
|PŘÍKAZOVÉHO ŘÁDKU|  
|PERFORMANCESUMMARY|  
|NOSUMMARY|  
|SHOWCOMMANDLINE|  
  
## <a name="see-also"></a>Viz také  
 [Vytváření předávajících (sekundárních) protokolovacích nástrojů](../msbuild/creating-forwarding-loggers.md)