---
title: 'DA0007: Vyhněte se použití výjimek pro tok řízení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.rules.DAExceptionsThrown
- vs.performance.7
- vs.performance.rules.DA0007
- vs.performance.DA0007
ms.assetid: ee8ba8b5-2313-46c9-b129-3f3a2a232898
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c4136df5f9a881a9c1df1234395d569d169d147
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670525"
---
# <a name="da0007-avoid-using-exceptions-for-control-flow"></a>DA0007: Vyhněte se použití výjimek pro tok řízení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DA0007: Vyhněte se použití výjimek pro tok řízení](https://docs.microsoft.com/visualstudio/profiling/da0007-avoid-using-exceptions-for-control-flow).  
  
Id pravidla | DA0007 |  
| Kategorie |. Použití rozhraní .NET Framework |  
| Metod profilace | Všechny |  
| Zpráva | Vysoký počet výjimek je vyvoláván. Zvažte snížení použití výjimek v logice programu. |  
| Typ zprávy | Upozornění |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit alespoň 25 vzorky k aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Vysoký počet obslužných rutin výjimek rozhraní .NET Framework byly volány v dat profilování. Zvažte použití další logiku toku řízení k omezení počtu výjimek, které jsou vyvolány.  
  
## <a name="rule-description"></a>Popis pravidla  
 Při použití obslužné rutiny výjimek pro zachycení chyb a další události, které narušují provádění programu je dobrým zvykem, použití obslužné rutiny výjimek jako součást pravidelných logika spuštění programu může být nákladné a mělo by se vyhnout. Ve většině případů by měla sloužit pouze pro okolnosti, které dochází zřídka a nepředpokládá výjimky... Výjimky by neměly používá k vrácení hodnoty jako součást toku typické programu. V mnoha případech se můžete vyhnout vyvolávání výjimek ověřování hodnoty a použitím podmíněnou logiku a zastavit provádění příkazů, které způsobují tento problém.  
  
 Další informace najdete v článku [Správa výjimek](http://go.microsoft.com/fwlink/?LinkID=177825) část **kapitola 5 – zvýšení výkonu kódu spravované** v **zlepšení výkonu aplikace .NET a škálovatelnost** objem **Microsoft Patterns and Practices** library na webu MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Zkoumání upozornění  
 Dvakrát klikněte na zprávu v okně Seznam chyb pro navigaci na zobrazení značky. Sloupec, který obsahuje najít **výjimky .NET CLR (@ProcessInstance)\\počet vyvolaných za sekundu** měření. Zjistěte, jestli konkrétní fáze spuštění programu se častěji než jiné zpracování výjimek. Pomocí vzorkování profilu, pokuste se identifikovat příkazy throw a try/catch – bloky, které generují se vyskytujících výjimek. V případě potřeby přidejte logiku pro bloky, které vám pomohou pochopit, výjimek, které jsou nejčastěji zpracovávanou catch. Kde je to možné, nahraďte často spouštěné příkazy throw nebo catch bloky s jednoduchý tok řízení logiku nebo ověřovací kód.  
  
 Například pokud chcete zjistit, že vaše aplikace zpracovával se vyskytujících výjimek dividebyzeroexception – přidání logiky pro váš program hledat jmenovateli s nulovými hodnotami zlepší výkon aplikace.



