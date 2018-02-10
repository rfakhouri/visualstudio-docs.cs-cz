---
title: "Analýza a modelování vaší architektury | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-modeling
ms.topic: get-started-article
helpviewer_keywords:
- Visual Studio Ultimate, exploring code
- Visual Studio Ultimate, visualizing code
- diagrams - modeling
- Visual Studio ALM, modeling
- application, design
- architecture
- code visualization
- application design
- applications, architecture
- code exploration
- Visual Studio ALM, exploring code
- modeling
- application architecture
- application, modeling
- applications, modeling
- architecture [Visual Studio ALM], modeling
- application modeling
- Visual Studio Ultimate, modeling
- architecture [Visual Studio Ultimate], modeling
- application, architecture
- Visual Studio ALM, visualizing code
- applications, designing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d1bcac24b0d0a5b14cbfbc082d8272ea846a1d54
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="analyze-and-model-your-architecture"></a>Analýza a modelování vaší architektury
Ujistěte se, že vaše aplikace splňuje požadavky architektury pomocí sady Visual Studio architektura a modelování nástroje pro návrh a modelování vaší aplikace. 

* Snadněji Pochopte stávající kód programu pomocí sady Visual Studio k vizualizaci struktury, chování a vztahy kódu. 

* Informujte váš tým potřebu respektováním architektury závislosti.  
  
* Vytváření modelů na různých úrovních podrobností v průběhu životního cyklu aplikací v rámci vývojových procesech.

V tématu [scénář: Změna návrhu pomocí vizualizace a modelování](../modeling/scenario-change-your-design-using-visualization-and-modeling.md).  
  
## <a name="to"></a>Chcete-li  
  
|||  
|-|-|  
|**Vizualizace kódu**:<br /><br /> – Zobrazí organizace a vztahy kódu vytvořením map kódu. Vizualizace závislosti mezi sestavení, obory názvů, třídy, metod a tak dále.<br />– Zobrazí struktura třídy a členy pro konkrétní projekt tak, že vytvoříte diagramů tříd z kódu.<br />-Vyhledání konflikty mezi váš kód a jeho návrhu vytvořením závislostí diagramy ověření kódu.|-   [Vizualizace kódu](../modeling/visualize-code.md)<br />-   [Práce s třídami a ostatními typy (návrhář tříd)](../ide/working-with-classes-and-other-types-class-designer.md)<br />-   [Video: Porozumět návrhu z kódu pomocí sady Visual Studio 2015 mapy kódu](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)<br />-   [Video: Ověření svoje závislosti architektury v reálném čase](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)|  
|**Definování architekturu**:<br /><br /> -Definovat a vynutit omezení závislosti mezi součástmi kódu tak, že vytvoříte diagramy závislostí.|-   [Video: Ověření závislosti architektury pomocí sady Visual Studio (Channel 9)](https://channel9.msdn.com/Events/Connect/2016/170)|  
|**Ověřování systému s požadavky a určen návrhu:**<br /><br /> -Ověření závislostem kódu pomocí diagramů závislostí, které popisují určený architekturu a zabránit změny, které může být v konfliktu s návrhu.|-   [Video: Ověření závislosti architektury pomocí sady Visual Studio (Channel 9)](https://channel9.msdn.com/Events/Connect/2016/170)|  
|**Sdílení modelů, diagramy a map kódu pomocí správy verzí Team Foundation**:<br /><br /> -Uveďte map kódu, projektů a diagramů deoendency ve správě verzí Team Foundation v, můžete je sdílet.| |  
|**Přizpůsobení modelů a diagramů**:<br /><br /> -Vytvořte vlastní jazyky specifické pro doménu.|-   [Modelování SDK pro Visual Studio – specifické pro doménu jazyky](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|  
|**Generování textu s použitím šablon T4**:<br /><br /> -Použít text bloky a logiku řízení uvnitř šablony pro vygenerování souborů založený na textu.<br /> – T4 šablony sestavení pomocí nástroje MSBuild zahrnuté v sadě Visual Studio|-   [Generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md)|

Informace, které verze sady Visual Studio podporují jednotlivé funkce, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)  
  
## <a name="types-of-models-and-their-uses"></a>Typy modelů a jejich použití  
  
|**Typ modelu a typické používá**|  
|-------------------------------------|  
|**Mapy kódu**<br /><br /> Kód mapuje nápovědy zobrazí organizace a vztahy do vašeho kódu.<br /><br /> Typické použití:<br /><br /> -Kontrola kódu programu, můžete lépe pochopit jeho strukturu a jeho závislé součásti, aktualizujte a odhadnout náklady na navrhované změny.<br /><br /> Další informace:<br /><br /> -   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)<br />-   [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)|  
|**Diagram závislostí**<br /><br /> Diagramy závislostí umožňují definovat strukturu aplikace jako sada vrstvy nebo je blokuje explicitní závislosti. Můžete spustit ověření ke zjištění konfliktu mezi závislosti v kódu a závislosti, které jsou popsané v diagramu závislostí.<br /><br /> Typické použití:<br /><br /> -Stabilizaci strukturu aplikace prostřednictvím celá řada změn průběhu své životnosti.<br />-Zjišťování konfliktů neúmyslnému závislostí před vrácením se změnami změny kódu.<br /><br /> Další informace:<br /><br /> -   [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md)<br />-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|  
|**Jazyk specifické pro doménu (DSL)**<br /><br /> DSL je zápis, který návrh pro konkrétní účel. V sadě Visual Studio je obvykle grafického rozhraní.<br /><br /> Typické použití:<br /><br /> -Generovat nebo nakonfigurujte částí aplikace. Práce se vyžaduje vyvíjet zápis a nástroje. Výsledkem mohou být lépe odpovídaly k vaší doméně než UML přizpůsobení.<br />-U velkých projektů nebo řádky produktů, kde je velikost investice do vývoje DSL a jeho nástroje vrácený jeho použití v více než jeden projekt.<br /><br /> Další informace:<br /><br /> -   [Modelování SDK pro Visual Studio – specifické pro doménu jazyky](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|  
  
## <a name="where-can-i-get-more-information"></a>Kde lze získat další informace?  
  
[Visual Studio vizualizace & modelování fóra nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)  
  
## <a name="see-also"></a>Viz také  
 [Co je nového](../modeling/what-s-new-for-design-in-visual-studio.md)   
 [Správa životního cyklu aplikací DevOps a](http://msdn.microsoft.com/Library/74a1f71d-7f23-4c71-8fd7-89ede614fab6)
