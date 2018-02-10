---
title: "Přesunout typu do odpovídající soubor refaktoring v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 62187c88fa2d2cf7ecf1b358fa0c03416be449a8
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>Přesunout typu do odpovídající soubor refaktoring

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje přesunout vybraný typ do samostatného souboru se stejným názvem.

**Kdy:** máte ve stejném souboru, který chcete použít k oddělení více tříd, struktur, rozhraní, atd.

**Důvod:** umístění více typů ve stejném souboru může být obtížné vyhledat tyto typy. Přesunutím typy souborů se stejným názvem bude kód čitelnější a snadný přechod.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text do název typu pro přesun:

   - C#:

    ![Zvýrazněný - C#](media/movetype-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný - jazyka Visual Basic](media/movetype-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*.cs** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
   - **Myš**
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*.cs** z místní okno náhledu, kde  *TypeName* je název typu, který jste vybrali.

   Typ je přesunuta do nový soubor s tímto názvem v rámci vašeho řešení.

   - C#:

    ![Vložené result - C#](media/movetype-result-cs.png)

   - Visual Basic:

    ![Vložené result - jazyka Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)