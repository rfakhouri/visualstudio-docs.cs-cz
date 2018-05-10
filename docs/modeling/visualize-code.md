---
title: Vizualizace kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- code, understanding
- code, visualizing
- code, exploring
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 027a73343683b7953e70b597a8f9a222b56eb01f
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="visualize-code"></a>Vizualizace kódu

Vizualizace a modelování nástroje v sadě Visual Studio můžete použít k vám pomůžou pochopit stávající kód a popisují vaše aplikace. Díky tomu můžete vizuálně zjistěte, jak může ovlivnit změny kódu a nápovědy vyhodnocení práci a rizik, které jsou výsledkem tyto změny. Příklad:

- Zjistit vztahy v kódu mapovat vizuálně těchto relací.

- Popsat váš systém architektura a zachovat kód konzistentní s jeho návrhu, vytváření diagramů závislostí a ověření kódu proti tyto diagramů.

- K popisu třídy, struktury, vytvořte diagramy tříd.

Tyto nástroje také můžete snadno komunikovat s uživateli, které jsou spojené s projektu.

Informace, které verze sady Visual Studio podporují jednotlivé funkce, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="what-do-you-want-to-do"></a>Co chcete udělat?

|||
|-|-|
|**Pochopení kódu a jeho vztahů:**<br /><br /> Mapovat vztahy mezi konkrétní části kódu.<br /><br /> Zobrazit přehled vztahy v kódu pro celé řešení.<br /><br /> **Poznámka:**: V této verzi sady Visual Studio, termín *Mapa kódu* slouží místě *graf závislostí*.|- [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)<br />- [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)<br />- [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)<br />- [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)|
|**Pochopení struktury třídy:**<br /><br /> Struktura třídy v projektu Vizualizujte vytvořením diagramů tříd z kódu.|[Postupy: Přidání diagramů tříd do projektů (Návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)|
|**Popisují návrhu vysoké úrovně systému a ověření kódu na tomto návrhu:**<br /><br /> Popisují návrhu vysoké úrovně systému a jeho závislosti určený vytvořením diagramy závislostí. Ověření kódu pro tento návrh a ujistěte se, že zůstaly konzistentní s návrh závislosti v kódu.|- [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />- [Diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md)<br />- [Diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md)<br />- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Externí zdroje

|**Kategorie**|**Odkazy**|
|------------------|---------------|
|**Fóra**|- [Visual Studio vizualizace a modelování nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)<br />- [Visual Studio vizualizace a modelování SDK (nástroje DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogy**|[Visual Studio ALM a Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=201340)|
|**Technické články a deníků**|[Architektura fórum MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>Viz také

- [Scénář: Změna návrhu pomocí vizualizace a modelování](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)
- [Analýza a modelování vaší architektury](../modeling/analyze-and-model-your-architecture.md)
- [Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)
- [Použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
