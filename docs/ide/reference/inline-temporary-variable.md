---
title: Nahraďte dočasnou proměnnou s hodnotou
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: a7c691efcc507212aa0649b6c4b4179fb8288f06
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946103"
---
# <a name="inline-a-temporary-variable-refactoring"></a>Vložená dočasná proměnná refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje odstranit dočasné proměnné a nahraďte ji metodou jeho hodnotu.

**Kdy:** Použijte dočasné proměnné díky těžší porozumět kódu.

**Proč:** Odebírá se dočasná proměnná mohou vytvořit, kód lépe čitelný.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístit textový kurzor myši do dočasné proměnné se nedá vložit:

   - C#:

       ![Zvýrazněný kód:C#](media/inline-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/inline-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem na kód a vybrat **rychlé akce a Refaktoringy** nabídky.

3. Vyberte **dočasná proměnná na řádku** z automaticky otevíraného okna okno náhledu.

   Odebrat proměnnou a její použití nahrazuje hodnotu proměnné.

   - C#:

      ![Výsledek inline-C#](media/inline-result-cs.png)

   - Visual Basic:

      ![Výsledek inline - jazyka Visual Basic](media/inline-result-vb.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)