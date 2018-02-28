---
title: "Zdroj – Přehled ovládacího prvku integrace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], about source control
ms.assetid: 3a46e4eb-e677-49c3-8647-d927d035a19a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dd7b6a48b00e8bef62ff801519fc35cdc163902d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-integration-overview"></a>Přehled integrace správy zdrojového kódu
Tato část porovná dva způsoby, jak integrovat do zdrojového kódu pro Visual Studio; Správa zdrojového kódu modulů Plug-in a VSPackage, která poskytuje řešením pro řízení zdrojového a označuje nové funkce správy zdrojového. Visual Studio umožňuje ruční přepínání mezi VSPackages zdrojového kódu a modulů plug-in programu zdroj ovládacího prvku a také automatického přepínání na základě řešení.  
  
## <a name="source-control-integration"></a>Integrace ovládacích prvků zdrojového  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]podporuje dva typy možností integrace zdroj ovládacího prvku. Ve všech verzích [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], stále můžete integrovat na zdroj ovládacího prvku Plug-in volání rozhraní API (dříve také označovány jako MSSCCI rozhraní API), která poskytuje funkce správy základní zdrojového při použití sady Visual Studio zdroj ovládacího prvku uživatelského rozhraní (na základě typu modulu plug-in UŽIVATELSKÉ ROZHRANÍ). Správa zdrojového kódu VSPackage na druhé straně poskytuje nové, hluboká integrace [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] cesty vhodné pro integrace ovládacích prvků zdrojového, která požaduje vysokou úroveň vyspělosti a nezávislé ve model řízení její zdroj.  
  
 ![Zdroj – Přehled ovládacího prvku](../../extensibility/internals/media/sourcectnrloverview.gif "SourceCtnrlOverview")  
  
## <a name="source-control-plug-in"></a>Modul Plug-in správy zdrojového kódu  
 Všechny verze sady Visual Studio podporují zdroj ovládacího prvku Plug-in API specifikace verze 1.2 jako cesta k integraci. Modul plug-in implementátor zdroj ovládacího prvku zapíše knihovny DLL, která implementuje funkce rozhraní API modulu Plugin zdroj ovládacího prvku pro integrace ovládacích prvků zdrojového a registrace, jak je popsáno v [vytvoření modulu Plugin zdroj ovládacího prvku](../../extensibility/internals/creating-a-source-control-plug-in.md). V tomto přístupu používá integrované vývojové prostředí (IDE) [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní pro dialogová okna, jako je například vrácení se změnami, najdete v článku věnovaném, stránky vlastností nástroje/Možnosti, panely nástrojů a zdroj ovládacího prvku glyfů. Stoprocentní rozhraní API ovládacího prvku Plug-in Zdroj zajistí snadnou integraci do sady Visual Studio a bezproblémové prostředí pro uživatele. To znamená, že modul plug-in správy zdroje musí implementovat většinu funkcí a zpětná volání, které jsou popsané v rozhraní API.  
  
 K implementaci modulu plug-in pomocí rozhraní API ovládacího prvku Plug-in Zdroj Správa zdrojového kódu, postupujte takto:  
  
1.  Vytvoření knihovny DLL, která implementuje funkce, zadaný v [moduly plug-in správy zdrojového kódu](../../extensibility/source-control-plug-ins.md).  
  
2.  Zaregistruje knihovnu DLL tak, že položky odpovídající registru (popsané v [postupy: Instalace modulu Plugin zdroj ovládacího prvku](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)).  
  
3.  Vytvoření pomocné rutiny uživatelského rozhraní a zobrazení po zobrazení výzvy řízení adaptér zdrojový balíček (součást sady Visual Studio, která zajišťuje funkce správy zdrojového prostřednictvím zdroj ovládacího prvku moduly Plugin)  
  
 V reakci na příkaz zdroj ovládacího prvku Visual Studio IDE uvede standardní uživatelské rozhraní pro základní operace a potom předá informace k řízení zdrojů modulu plug-in prostřednictvím funkcí definovaných v rozhraní API ovládacího prvku Plug-in zdroje. Pro rozšířené možnosti modul plug-in správy zdroje může být volána na k představení vlastního uživatelského rozhraní, například procházení pro projekt řízené zdroje. To znamená, že uživatel může bude nabídnuta dvě by mohl mít jiný styly uživatelského rozhraní při plánování práce s zdrojového kódu: uživatelské rozhraní, které představuje Visual Studio a uživatelské rozhraní, které představuje modul plug-in zdrojového kódu. Toto je nejvíce patrné s operace ovládacího prvku rozšířené zdroje.  
  
### <a name="drawbacks-to-implementing-a-source-control-plug-in"></a>Nevýhody pro implementaci modulu Plug-in Správa zdrojového kódu  
  
-   Pro pokročilé funkce může uživatel vidět dvě různé styly rozhraní, což možné nejasnostem.  
  
-   Modul plug-in zdrojového kódu se jen ovládacího prvku modelu zdroje implicitní rozhraním API Plug-in Zdroj ovládacího prvku.  
  
-   Rozhraní API ovládacího prvku Plug-in Zdroj může být příliš omezující pro některých scénářích správy zdrojového kódu.  
  
### <a name="advantages-to-implementing-a-source-control-plug-in"></a>Výhody implementace modulu Plug-in Správa zdrojového kódu  
  
-   Visual Studio poskytuje uživatelské rozhraní pro všechny operace základní zdroj ovládacího prvku tak, aby modul plug-in správy zdroje nemá k implementaci potenciálně složité uživatelského rozhraní.  
  
-   Z důvodu striktní rozhraní API modul plug-in zdrojového kódu můžete snadno komunikovali s programy řízení externí zdroj nakonfigurovánu rozsáhlejší; Visual Studio nijak nereaguje, příliš mnohem jak se funkce správy zdrojů se provádí, pouze to, že se provádí podle rozhraní API ovládacího prvku Plug-in zdroje.  
  
-   Je jednodušší implementaci ovládacího prvku zdroj modulu plug-in než VSPackage Správa zdrojového kódu.  
  
## <a name="source-control-vspackage"></a>VSPackage zdroj ovládacího prvku  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]Umožňuje těsná integrace do sady Visual Studio s plnou kontrolu nad funkce správy zdrojového a úplné nahrazení uživatelského rozhraní pro řízení zdrojového poskytované sadě Visual Studio. Správa zdrojového kódu VSPackage je zaregistrován pomocí sady Visual Studio a poskytuje funkce správy zdrojového. I když několik zdrojového kódu VSPackages lze registrovat pomocí sady Visual Studio, pouze jedna z nich můžou být aktivní v daném okamžiku. Správa zdrojového kódu VSPackage má plnou kontrolu nad funkce správy zdrojového a vzhled v sadě Visual Studio, i když je aktivní. Všechny ostatní zdrojového kódu VSPackages zaregistrované v systému nejsou aktivní a které nezobrazí žádné uživatelské rozhraní vůbec.  
  
 Implementace Správa zdrojového kódu VSPackage vyžaduje strategie "všechny nebo nic". Tvůrce zdrojového kódu VSPackage musí investovat významné množství úsilí v jeho implementaci počet rozhraní pro řízení zdrojového a nové prvky uživatelského rozhraní (dialogových oken, nabídek a panelů nástrojů) tak, aby pokrývalo funkci řízení celý zdrojový. V tématu [vytváření VSPackage řízení zdroj](../../extensibility/internals/creating-a-source-control-vspackage.md) další podrobnosti.  
  
### <a name="drawbacks-to-implementing-a-source-control-vspackage"></a>Nevýhody pro implementaci VSPackage zdroj ovládacího prvku  
  
-   VSPackage musí implementovat několik komplexní rozhraní pro integraci úspěšně pomocí sady Visual Studio.  
  
-   VSPackage musíte zadat všechna rozhraní požadované pro řízení zdrojů; Visual Studio bude poskytovat žádné pomoc v této oblasti.  
  
-   Správa zdrojového kódu VSPackage důvěrně je vázaný na Visual Studio a nemůže pracovat s samostatné programy, proto funkce nemohou být sdíleny s externí verzi zdrojový program řízení snadno.  
  
### <a name="advantages-to-implementing-a-source-control-vspackage"></a>Výhody pro implementaci VSPackage zdroj ovládacího prvku  
  
-   Protože VSPackage má plnou kontrolu nad zdrojového kódu uživatelského rozhraní a funkcí, zobrazí se uživateli bezproblémové rozhraní pro řízení zdrojů.  
  
-   VSPackage není omezen na konkrétní zdroj ovládacího prvku modelu.  
  
## <a name="see-also"></a>Viz také  
 [Správa zdrojového kódu](../../extensibility/internals/source-control.md)   
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [Vytvoření ovládacího prvku VSPackage zdroje](../../extensibility/internals/creating-a-source-control-vspackage.md)   
 [Co je nového ve správě zdrojového kódu](../../extensibility/internals/what-s-new-in-source-control.md)