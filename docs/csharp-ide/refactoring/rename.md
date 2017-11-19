---
title: "Přejmenování - refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 60e2a623-b56d-4591-93dc-e51429e4e1ba
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.rename
dev_langs: CSharp
ms.openlocfilehash: c89aae8e6e0f43ee2083bba46f2bbeeadd488535
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="rename-a-code-symbol-in-c"></a>Přejmenujte symbol kódu v jazyce C# #
**Co:** umožňuje přejmenovat identifikátory pro kód symboly, například pole, místní proměnné, metody, obory názvů, vlastnosti a typy.

**Kdy:** chcete bezpečně něco přejmenovat bez nutnosti vyhledáte všechny instance a zkopírujte a vložte nový název.  

**Důvod:** kopírování a vkládání nový název napříč celý projekt by pravděpodobně vést k chybám.  Tento nástroj refaktoringu přesně provede přejmenování akce.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor textu uvnitř položky k přejmenování:

   ![Zvýrazněný kód](media/rename_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **Ctrl + R**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > přejmenujte**.
     * Klikněte pravým tlačítkem na kód a vyberte **přejmenovat**.

1. Přejmenujte položce jednoduše tak, že zadáte nový název.

   ![Přejmenujte animace](media/rename_animated.gif)

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců používat tento nový název, a také [zobrazení náhledu změn](../../ide/preview-changes.md) před uložením pomocí zaškrtávacích políček v **přejmenovat** pole, která se zobrazí v horní části napravo od vaší IDE.

1. Jakmile budete spokojeni se změnami, klikněte na **použít** tlačítko nebo klikněte na tlačítko **Enter** a změny budou potvrzeny.

> [!NOTE]
> Pokud použijete název, který již existuje, které by způsobily konflikt, který **přejmenovat** pole v vaší IDE zobrazí upozornění.
>
> ![Přejmenování konflikt](media/rename_conflict.png)

## <a name="see-also"></a>Viz také  
[Refaktoring (C#)](../refactoring-csharp.md)  
[Zobrazení náhledu změn](../../ide/preview-changes.md)
