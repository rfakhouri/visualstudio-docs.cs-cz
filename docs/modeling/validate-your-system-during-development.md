---
title: Ověřování systému během vývoje
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d4ebc815f474f1b8a1c59c9736f9014ba02e523
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="validate-your-system-during-development"></a>Ověřování systému během vývoje
Visual Studio může pomoct Udržujte software konzistentní s požadavky na uživatele a architektuře systému.

 Jaké verze sady Visual Studio podporovat každé z těchto funkcí najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="key-tasks"></a>Klíčové úlohy
 Pomocí následujících úloh ověření vašeho softwaru.

|**Úlohy**|**Související témata**|
|---------------|---------------------------|
|**Zajistěte, aby váš software splňuje požadavky uživatelů**:<br /><br /> Požadavky a architektury modely můžete uspořádat testy systému a jeho součástí. Tento postup pomáhá, zajistěte, aby test požadavky, které jsou důležité pro uživatele a dalších zúčastněných osob a pomůže vám rychle aktualizovat testy při změně požadavky.|-   [Vývoj testů z modelu](../modeling/develop-tests-from-a-model.md)|
|**Ujistěte se, že váš software konzistentní s určený návrh vašeho systému:**<br /><br /> Diagramy závislostí popisují určený závislostí mezi součástmi aplikace. Během vývoje můžete ověřit, že skutečné závislosti v kódu odpovídají zamýšlené.|-   [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Externí zdroje

|**Kategorie**|**Odkazy**|
|------------------|---------------|
|**Videa**|![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Doug sedm: pochopení kódu a návrhu systému sadou Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: architektury aplikace pomocí Diagram závislostí](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [MSDN How do I řady: postup ověření kódu pomocí diagramů závislostí](http://go.microsoft.com/fwlink/?LinkID=214405)|
|**Fóra**|-   [Visual Studio vizualizace a modelování nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio vizualizace a modelování SDK (nástroje DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogy**|-   [Visual Studio ALM a Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=201340)|
|**Technické články a deníků**|[Architektura softwaru MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>Viz také

- [Testování aplikace](https://www.visualstudio.com/en-gb/docs/test/overview)
- [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)
- [Analýza a modelování vaší architektury](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
