---
title: Rozšíření diagramů závislostí
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 39d8324479e390d76e25f2c7187ed2c184d3af04
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="extend-dependency-diagrams"></a>Rozšíření diagramů závislostí
Můžete napsat kód k vytvoření a aktualizaci diagramy závislostí a k ověření strukturu svůj kód programu s diagramy závislosti v sadě Visual Studio. Můžete přidat příkazy, které jsou uvedeny v nabídce zástupce (kontextu) diagramy, přizpůsobit gesta přetahování myší a přístup k vrstvě modelu z textové šablony. Můžete balíček tato rozšíření do Visual Studio integrace rozšíření (VSIX) a distribuujte je do jiných uživatelů v sadě Visual Studio.

 Další informace o závislostech diagramy najdete v části:

-   [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)

-   [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)

-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)

-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)

##  <a name="prereqs"></a> Požadavky
 Musíte mít nainstalované v počítači, ve které chcete vyvíjet rozšíření vrstvy tyto položky:

-   Visual Studio

-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

-   Modelování SDK pro Visual Studio


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 Musí mít vhodná verze sady Visual Studio nainstalována v počítači, kde chcete spustit rozšíření vrstvy. Další informace najdete v tématu [nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md).

 Informace, které verze sady Visual Studio podporují závislostí diagramy, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="in-this-section"></a>V tomto oddílu
 [Přidávání příkazů a gest do diagramů závislostí](../modeling/add-commands-and-gestures-to-layer-diagrams.md)

 [Přidání vlastního ověřování architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)

 [Přidání vlastních vlastností do diagramů závislostí](../modeling/add-custom-properties-to-layer-diagrams.md)

 [Procházení a aktualizace modelů vrstev v programovém kódu](../modeling/navigate-and-update-layer-models-in-program-code.md)

 [Nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md)

 [Řešení potíží s rozšířeními pro diagramy závislostí](../modeling/troubleshoot-extensions-for-layer-diagrams.md)

## <a name="see-also"></a>Viz také

- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)
- [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)
- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)
