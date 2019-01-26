---
title: Přejmenujte název souboru tak, aby odpovídaly typu
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 4625d8c4b6bce3235fe07682cb6a0e977258adf6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948177"
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-refactoring"></a>Synchronizace typu název souboru nebo název souboru pro typ refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje přejmenujte typ tak, aby odpovídaly názvu souboru, nebo název souboru tak, aby odpovídaly typu, který ji obsahuje.

**Kdy:** Přejmenování souboru nebo typu a ještě neprovedli aktualizaci na odpovídající soubor nebo typ k porovnání.

**Proč:** Typ umístění v souboru s jiným názvem, nebo naopak je obtížné najít, co hledáte. Přejmenováním tento typ nebo název souboru bude kód čitelnější a přehlednější a díky tomu.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text mezi název typu pro synchronizaci:

   - C#:

       ![Zvýrazněný kód:C#](media/synctype-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/synctype-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **přejmenování souboru *TypeName*.cs** z místní nabídka okna ve verzi Preview, kde *TypeName* je název vybraného typu.
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **Přejmenovat typ na _Filename_**  z místní nabídka okna ve verzi Preview, kde *Filename* je název aktuálního souboru.
   - **Myši**
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **přejmenování souboru *TypeName*.cs** z místní nabídka okna ve verzi Preview, ve kterém *TypeName* je název vybraného typu.
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **Přejmenovat typ na _Filename_**  z místní nabídka okna ve verzi Preview, ve kterém  *Název souboru* je název aktuálního souboru.

   Přejmenování nebo typu souboru.

   - C#: V příkladu níže, soubor **MyClass.cs** se přejmenoval na **MyNewClass.cs** tak, aby odpovídaly názvu typu.

       ![Vložené výsledekC#](media/synctype-result-cs.png)

   - Visual Basic: V příkladu níže, soubor **Employee.vb** se přejmenoval na **Person.vb** tak, aby odpovídaly názvu typu.

       ![Vložené výsledek jazyka Visual Basic](media/synctype-result-vb.png)

> ! [POZNÁMKA] Tento refaktoring ještě není k dispozici pro projekty .NET Standard a .NET Core.

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
