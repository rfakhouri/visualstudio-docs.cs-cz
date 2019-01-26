---
title: Nahraďte dočasnou proměnnou s hodnotou
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
ms.openlocfilehash: 37a70dd119cf94bf79796cdc0684c8dbee47032c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991259"
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