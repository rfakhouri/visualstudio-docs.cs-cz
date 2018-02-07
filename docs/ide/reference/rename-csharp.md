---
title: "Refaktorovat přejmenovat v sadě Visual Studio pro jazyk C# | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e1325de81e16b0e381f07af4d8073d0a3fa4330c
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="rename-a-code-symbol-in-c"></a>Přejmenujte symbol kódu v jazyce C# #

**Co:** umožňuje přejmenovat identifikátory pro kód symboly, například pole, místní proměnné, metody, obory názvů, vlastnosti a typy.

**Kdy:** chcete bezpečně něco přejmenovat bez nutnosti vyhledáte všechny instance a zkopírujte a vložte nový název.

**Důvod:** kopírování a vkládání nový název napříč celý projekt by pravděpodobně vést k chybám.  Tento nástroj refaktoringu přesně provede přejmenování akce.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor textu uvnitř položky k přejmenování:

   ![Zvýrazněný kód](media/rename-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **Ctrl + R**. (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > přejmenujte**.
     * Klikněte pravým tlačítkem na kód a vyberte **přejmenovat**.

1. Přejmenujte položce jednoduše tak, že zadáte nový název.

   ![Přejmenujte animace](media/rename-animated-cs.gif)

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců používat tento nový název, a také [zobrazení náhledu změn](../../ide/preview-changes.md) před uložením pomocí zaškrtávacích políček v **přejmenovat** pole, která se zobrazí v horní části napravo od vaší IDE.

1. Jakmile budete spokojeni se změnami, klikněte na **použít** tlačítko nebo klikněte na tlačítko **Enter** a změny budou potvrzeny.

> [!NOTE]
> Pokud použijete název, který již existuje, které by způsobily konflikt, který **přejmenovat** pole v vaší IDE zobrazí upozornění.
>
> ![Přejmenování konflikt](media/rename-conflict-cs.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)
