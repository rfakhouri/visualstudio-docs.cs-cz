---
title: Refaktorovat přejmenovat v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 696ec34bb0009b9b09b5902a102c71cf1331f320
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="rename-a-code-symbol-refactoring"></a>Symbol kódu refaktoring pro přejmenování

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje přejmenovat identifikátory pro kód symboly, například pole, místní proměnné, metody, obory názvů, vlastnosti a typy.

**Kdy:** chcete bezpečně něco přejmenovat bez nutnosti vyhledáte všechny instance a zkopírujte a vložte nový název.

**Důvod:** kopírování a vkládání nový název napříč celý projekt by pravděpodobně vést k chybám. Tento nástroj refaktoringu přesně provede přejmenování akce.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor textu uvnitř položky k přejmenování:

   - C#:

    ![Zvýrazněný - C#](media/rename-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný - jazyka Visual Basic](media/rename-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl + R**, pak **Ctrl + R**. (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
   - **Myš**
     - Vyberte **Upravit > Refaktorovat > přejmenujte**.
     - Klikněte pravým tlačítkem na kód a vyberte **přejmenovat**.

1. Přejmenujte položce jednoduše tak, že zadáte nový název.

   - C#:

    ![Přejmenujte animace – C#](media/rename-animated-cs.gif)

   - Visual Basic:

    ![Přejmenování - jazyka Visual Basic](media/rename-rename-vb.png)

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců používat tento nový název, a také [zobrazit náhled změn](../../ide/preview-changes.md) před uložením pomocí zaškrtávacích políček v **přejmenovat** pole, která se zobrazí v horní části napravo od vaší editor.

1. Až budete spokojeni se změnami, vyberte **použít** tlačítko nebo klikněte na tlačítko **Enter** a změny budou potvrzeny.

> [!NOTE]
> Pokud použijete název, který již existuje, které by způsobily konflikt, který **přejmenovat** pole zobrazí upozornění.
>
> ![Přejmenování konflikt](media/rename-conflict-cs.png)

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
