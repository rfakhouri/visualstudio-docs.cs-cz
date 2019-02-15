---
title: Ověřování systému během vývoje
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce0822f5731e7c09a6f6dff9116e70b97a529206
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316753"
---
# <a name="validate-your-system-during-development"></a>Ověřování systému během vývoje
Visual Studio vám může pomoci udržovat konzistentní s požadavky uživatelů a architektuře systému vašeho softwaru.

 Které verze sady Visual Studio podporovat každé z těchto funkcí najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="key-tasks"></a>Klíčové úkoly
 Tyto úlohy slouží k ověření vašeho softwaru.

|**Úlohy**|**Související témata**|
|-|-|
|**Ujistěte se, že software splňuje požadavky uživatelů**:<br /><br /> Požadavky a architektury modely můžete pomoci vám organizovat testy systému a jeho součástí. Tento postup pomáhá zajistit, že testování požadavků, které jsou důležité pro uživatele a další zainteresované uživatele, a pomůže vám rychle aktualizovat testů při změně požadavků.|-   [Vývoj testů z modelu](../modeling/develop-tests-from-a-model.md)|
|**Ujistěte se, že software zůstává konzistentní s zamýšleného návrhu systému:**<br /><br /> Diagramy závislostí popsat zamýšlené závislosti mezi komponentami vaší aplikace. Během vývoje můžete ověřit, že skutečné závislosti v kódu odpovídají zamýšleného návrhu.|-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Externí zdroje

|**Kategorie**|**Odkazy**|
|-|-|
|**Videa**|![odkaz na video](../data-tools/media/playvideo.gif) [Channel 9: Doug sedm: Porozumění kódu a návrhu systému sadou Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif) [Channel 9: Aplikační architektura založená na aplikaci pomocí Diagram závislostí](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif) [řady MSDN jak: Postup ověření kódu pomocí diagramů závislostí](http://go.microsoft.com/fwlink/?LinkID=214405)|
|**Fóra**|-   [Visual Studio Visualization & Modeling nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Visualization & Modeling SDK (DSL Tools)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogy**|-   [Microsoft DevOps](https://devblogs.microsoft.com/devops/)|
|**Technické články a deníky**|[MSDN Architecture Center](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>Viz také:

- [Testování aplikace](/azure/devops/test/overview?view=vsts)
- [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)
- [Analýza a modelování architektury](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
