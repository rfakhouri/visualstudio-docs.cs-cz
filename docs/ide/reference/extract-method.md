---
title: Extrahovat metodu
description: Zapněte fragment kódu do své vlastní metody, a to tak, že vyberete kód a zadáte CTRL + R, CTRL + M.
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.extractmethod
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: a764fd0d95696866e914ec76a560a49d641acb47
ms.sourcegitcommit: 0f5f7955076238742f2071d286ad8e896f3a6cad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68483662"
---
# <a name="extract-a-method-refactoring"></a>Extrahovat metodu refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje přepínat fragment kódu na svou vlastní metodu.

**Kdy:** Máte fragment stávajícího kódu v některé metodě, který je třeba volat z jiné metody.

**Proč:** Tento kód můžete zkopírovat nebo vložit, ale to by vedlo k duplikaci. Lepším řešením je refaktorovat tohoto fragmentu do své vlastní metody, které je možné vyvolat volně jiným způsobem.

## <a name="how-to"></a>Postupy

1. Zvýraznění kódu extrahovaným:

   - C#:

       ![Zvýrazněný kód –C#](media/extractmethod-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/extractmethod-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl + R**, pak **Ctrl + M**. (Všimněte si, že klávesová zkratka může být jiný platformě, na který profil vyberete.)
      - Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **extrahovat metodu** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Vyberte **Upravit > Refaktorovat > extrahovat metodu**.
      - Klikněte pravým tlačítkem na kód a vybrat **Refaktorovat > extrahovat > extrahovat metodu**.
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **extrahovat metodu** z automaticky otevíraného okna okno náhledu.

   Metoda se okamžitě vytvoří. Z tohoto místa můžete nyní přejmenovat metodu jednoduše tak, že zadáte nový název.

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců použít tento nový název, stejně jako [náhled změn](../../ide/preview-changes.md) před uložením používání zaškrtávacích políček v **přejmenovat** pole, které se zobrazí v horní části napravo od prostředí (IDE).

   - C#:

      ![Přejmenovat metodu-C#](media/extractmethod-rename-cs.png)

   - Visual Basic:

      ![Přejmenovat metodu - jazyka Visual Basic](media/extractmethod-rename-vb.png)

3. Až budete spokojení s změny, zvolte **použít** tlačítko nebo stisknutím klávesy **Enter** a změny budou potvrzeny.

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)