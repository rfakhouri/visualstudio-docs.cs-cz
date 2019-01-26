---
title: Rozšíření diagramů závislostí
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 04aa7c1948cd07bf49ab754619442e5310b023f9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069131"
---
# <a name="extend-dependency-diagrams"></a>Rozšíření diagramů závislostí
Můžete napsat kód k vytvoření a aktualizaci diagramů závislostí a k ověření struktury kód programu proti diagramů závislostí v sadě Visual Studio. Můžete přidat příkazy, které se zobrazují v nabídce místní (objektu context) diagramů, přizpůsobení gesta přetažení myší a přístup k modelu vrstvy z textových šablon. Můžete zabalit tato rozšíření do Visual Studio integrace rozšíření (VSIX) a distribuovat ostatním uživatelům aplikace Visual Studio.

 Další informace o diagramů závislostí naleznete v tématu:

-   [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)

-   [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)

-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)

-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)

##  <a name="prereqs"></a> Požadavky
 Musí být nainstalovaný na počítači, kde chcete vyvíjet rozšíření vrstvy:

-   Visual Studio

-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

-   Sada Modeling SDK pro Visual Studio


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 Musí mít vhodnou verzi sady Visual Studio nainstalované na počítači, ve kterém chcete spustit rozšíření vrstvy. Další informace najdete v tématu [nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md).

 Které verze sady Visual Studio podporují diagramů závislostí najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="in-this-section"></a>V tomto oddílu
 [Přidávání příkazů a gest do diagramů závislostí](../modeling/add-commands-and-gestures-to-layer-diagrams.md)

 [Přidání vlastního ověřování architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)

 [Přidání vlastních vlastností do diagramů závislostí](../modeling/add-custom-properties-to-layer-diagrams.md)

 [Procházení a aktualizace modelů vrstev v programovém kódu](../modeling/navigate-and-update-layer-models-in-program-code.md)

 [Nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md)

 [Řešení potíží s rozšířeními pro diagramy závislostí](../modeling/troubleshoot-extensions-for-layer-diagrams.md)

## <a name="see-also"></a>Viz také

- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)
- [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)
- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)
