---
title: Přejmenujte název souboru tak, aby odpovídaly typu v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 58a4a1647912203fd1415176f4089904f8c70e0f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-refactoring"></a>Zadejte název souboru nebo název souboru, do typu refaktoring synchronizace

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje přejmenujte typ k porovnání název souboru, nebo název souboru tak, aby odpovídaly typ obsahuje.

**Kdy:** přejmenovaná souboru nebo typ a ještě neprovedli aktualizaci na odpovídající soubor nebo typ k porovnání.

**Důvod:** umístění a typ v souboru s jiným názvem nebo naopak, je obtížné najít, co hledáte. Přejmenováním typ nebo název souboru, bude kód čitelnější a snadný přechod.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text do název typu synchronizovat:

   - C#:

    ![Zvýrazněný - C#](media/synctype-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný - jazyka Visual Basic](media/synctype-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přejmenování souboru *TypeName*.cs** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
     - Stiskněte klávesu **Ctrl**+**.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **Přejmenovat typ _Filename_**  z místní okno náhledu, kde *Filename* je název aktuálního souboru.
   - **Myš**
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **přejmenování souboru *TypeName*.cs** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **Přejmenovat typ _Filename_**  z místní okno náhledu, kde  *Název souboru* je název aktuálního souboru.

   Typ nebo souboru je přejmenovat.

   - C#: V příkladu níže soubor **MyClass.cs** byla přejmenována na **MyNewClass.cs** tak, aby odpovídaly název typu.

      ![Vložené výsledek C#](media/synctype-result-cs.png)

   - Visual Basic: V příkladu níže soubor **Employee.vb** byla přejmenována na **Person.vb** tak, aby odpovídaly název typu.

      ![Vložené výsledek jazyka Visual Basic](media/synctype-result-vb.png)

> ! [POZNÁMKA] Tato refaktoring ještě není k dispozici pro projekty .NET Standard a .NET Core.

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
