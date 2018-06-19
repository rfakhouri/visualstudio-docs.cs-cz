---
title: Implementace rozhraní v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 4b17e924a6736d37b78709a516f6ca9068d4711c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946439"
---
# <a name="implement-an-interface-in-visual-studio"></a>Implementace rozhraní v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu potřebnou k implementaci rozhraní.

**Kdy:** chcete použít dědění z rozhraní.

**Důvod:** může ručně implementovat všechny rozhraní jeden po druhém, ale tato funkce bude automaticky generovat všechny podpisy metoda.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází red vlnovka, označující odkazujete rozhraní, ale ještě implementována všechny požadované členy.

   - C#:

    ![Zvýrazněný kód C#](media/interface-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/interface-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

1. Vyberte **implementovat rozhraní** z rozevírací nabídky.

   ![Implementace rozhraní preview](media/interface-preview-cs.png)

   > [!TIP]
   > - Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.
   > - Použití **dokumentu**, **projektu**, a **řešení** odkazy v dolní části okna náhledu k vytvoření podpisy správné metody napříč více tříd, které implementují rozhraní.

   Podpisy metoda v rozhraní je vytvořen a je připravený k implementaci.

   - C#:

      ![Implementace rozhraní výsledek C#](media/interface-result-cs.png)

   - Visual Basic:

      ![Implementace rozhraní výsledek jazyka Visual Basic](media/interface-result-vb.png)

   > [!TIP]
   > (C# pouze) Použití **implementovat rozhraní explicitně** možnost Adresa každý generované metodu s názvem rozhraní tak, aby se zabránilo kolize názvů.
   >
   > ![Implementovat rozhraní explicitně dojít.](media/interface-explicitresult-cs.png);

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)