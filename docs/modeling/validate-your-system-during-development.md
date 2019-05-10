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
ms.openlocfilehash: 9fb9810f1c212dfb881f5725676a79c6307b9cfa
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476508"
---
# <a name="validate-your-system-during-development"></a>Ověřování systému během vývoje

Visual Studio vám může pomoci udržovat konzistentní s požadavky na uživatele a architektuře systému vašeho softwaru.

Které verze sady Visual Studio podporovat každé z těchto funkcí najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="key-tasks"></a>Klíčové úkoly

K ověření vašeho softwaru, použijte následující úlohy:

|**Úlohy**|**Související témata**|
|-|-|
|**Ujistěte se, že software splňuje požadavky uživatelů**:<br /><br />Pomocí požadavků a architektury modely můžete organizovat testy systému a jeho součástí. Tento postup pomáhá zajistit, že testování požadavků, které jsou důležité pro uživatele a další zainteresované uživatele, a pomůže vám rychle aktualizovat testů při změně požadavků.|- [Vývoj testů z modelu](../modeling/develop-tests-from-a-model.md)|
|**Ujistěte se, že software zůstává konzistentní s zamýšleného návrhu systému:**<br /><br />Diagramy závislostí popsat zamýšlené závislosti mezi komponentami vaší aplikace. Během vývoje můžete ověřit, že skutečné závislosti v kódu odpovídají zamýšleného návrhu.|- [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Externí zdroje

|**Kategorie**|**Odkazy**|
|-|-|
|**Videa**|![odkaz na video](../data-tools/media/playvideo.gif) [Channel 9: Doug sedm: Porozumění kódu a navrhování systémů pomocí Visual Studio 2010](https://channel9.msdn.com/shows/VS2010Launch/Doug-Seven-Code-Understanding-and-Systems-Design-with-Visual-Studio-2010)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif) [Channel 9: Aplikační architektura založená na aplikaci](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-5-architecting-an-application))|
|**Fóra**|- [Visual Studio Visualization & Modeling nástroje](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch)<br />- [Rozšíření produktu Visual Studio](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx)|

## <a name="see-also"></a>Viz také:

- [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)
- [Analýza a modelování architektury](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
