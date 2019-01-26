---
title: Čtení modelů a diagramů v jiných edicích sady Visual Studio
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 0f050efd1e85d707ed0542ee5e1254fdaa3241b4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55068680"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Čtení modelů a diagramů v jiných edicích sady Visual Studio

Při otevření modelu ve verzi sady Visual Studio, který nepodporuje vytvoření modelu, model otevře v režimu jen pro čtení. V tomto režimu můžete změnit rozložení diagramy, ale nemůže změnit model.

Které verze sady Visual Studio podporují vytváření modelu najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Získání přístupu k modelu a diagramů

Další diagram závislostí, musíte nejdřív pomocí sady Visual Studio otevřete projekt modelování a pak otevřete diagram v něm.

Z tohoto důvodu Pokud si chcete přečíst diagram závislostí, musí máte také přístup k projektu modelování, ve kterém byla vytvořena. Můžete provést buď díky přístupu do projektu ze správy zdrojových kódů, nebo prostřednictvím provedeného kopírování souborů projektu.

> [!NOTE]
> Tato akce není požadována kódu mapy a .NET třídy diagramy generované z kódu. Tyto diagramy lze zobrazit nezávisle na projektu modelování.

Další diagram závislostí, je minimální sadu souborů, které budete potřebovat následující:

-   Dva soubory pro diagram, který si chcete přečíst, například diagramů **MyDiagram.classdiagram a MyDiagram.classdiagram.layout**.

    > [!NOTE]
    > Pro diagramy závislostí, také byste měli mít soubor s názvem _MyDiagram_**. layerdiagram.suppressions**.

-   Soubor projektu modelování (**MyModel.modelproj**)

-   V kořenovém souboru modelu (**ModelDefinition\MyModel.uml**)

-   Soubory balíčku pro všechny balíčky odkazované v diagramu (**ModelDefinition\MyPackage.uml**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Změny provedené v režimu jen pro čtení

Pokud otevřete modelu a jeho diagramy v verzi sady Visual Studio, která nepodporuje vytváření modelu, nelze změnit model. To znamená nelze změnit na prvky a vztahy, které jsou zobrazeny v diagramech nebo v Průzkumníku modelů. Můžete ale proveďte nějaké změny rozložení diagramy:

- Změna uspořádání obrazců a konektorů v diagramu.

- Rozbalit nebo sbalit obrazce.

Je-li uložit tyto změny. Pokud chcete provádět změny viditelné pro ostatní uživatele, minimálně, odešlete aktualizovaný **.layout** soubory.

## <a name="see-also"></a>Viz také

- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md)