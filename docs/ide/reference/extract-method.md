---
title: "Extrahování metody v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.extractmethod
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 4ccdab053e06efc11b6f9c42d391d4b4fc1f85f7
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="extract-a-method-refactoring"></a>Extrahování metody refaktoring

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje zapnout fragment kódu do své vlastní metody.

**Kdy:** máte fragment kódu existující v některé metody, které musí být volána z jiné metody.

**Důvod:** vám může zkopírujte a vložte tento kód, ale které by vedlo k duplikaci. Lepší řešení je refaktorovat tento fragment do vlastní metodu, která můžete volně volána jiným způsobem.

## <a name="how-to"></a>Postupy

1. Zvýrazněte kód extrahovat:

   - C#:

    ![Zvýrazněný kód – C#](media/extractmethod-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný - jazyka Visual Basic](media/extractmethod-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl + R**, pak **Ctrl + M**. (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     - Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **extrahovat metodu** z okna náhledu – místní nabídka.
   - **Myš**
     - Vyberte **Upravit > Refaktorovat > extrahování metody**.
     - Klikněte pravým tlačítkem na kód a vyberte **Refaktorovat > extrahovat > extrahovat metodu**.
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **extrahovat metodu** z okna náhledu – místní nabídka.

   Metoda se okamžitě vytvoří. Tady můžete nyní přejmenovat metoda jednoduše tak, že zadáte nový název.

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců používat tento nový název, a také [zobrazení náhledu změn](../../ide/preview-changes.md) před uložením pomocí zaškrtávacích políček v **přejmenovat** pole, která se zobrazí v horní části napravo od vaší IDE.

   - C#:
   
    ![Přejmenujte metoda - C#](media/extractmethod-rename-cs.png)

   - Visual Basic:
   
    ![Přejmenujte metodu – Visual Basic](media/extractmethod-rename-vb.png)

1. Až budete spokojeni se změnami, vyberte **použít** tlačítko nebo klikněte na tlačítko **Enter** a změny budou potvrzeny.

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)