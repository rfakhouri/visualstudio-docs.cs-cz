---
title: Rozšíření diagramů závislostí
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c164174b88ca9fdd815668084c1447e20de072c
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476571"
---
# <a name="extend-dependency-diagrams"></a>Rozšíření diagramů závislostí

Můžete napsat kód k vytvoření a aktualizaci diagramů závislostí a k ověření struktury kód programu proti diagramů závislostí v sadě Visual Studio. Můžete přidat příkazy, které se zobrazují v nabídce místní (objektu context) diagramů, přizpůsobení gesta přetažení myší a přístup k modelu vrstvy z textových šablon. Můžete zabalit tato rozšíření do Visual Studio integrace rozšíření (VSIX) a distribuovat ostatním uživatelům aplikace Visual Studio.

## <a name="requirements"></a>Požadavky

Musí být nainstalovaný na počítači, kde chcete vyvíjet rozšíření vrstvy:

- Visual Studio

- [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

- Sada Modeling SDK pro Visual Studio

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

Musíte mít vhodný edici sady Visual Studio nainstalované na počítači, ve kterém chcete spustit rozšíření vrstvy. Chcete-li zjistit, jaké edice sady Visual Studio podporují diagramů závislostí, přečtěte si téma [podpora edice nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="see-also"></a>Viz také:

- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)
- [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)
- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)
