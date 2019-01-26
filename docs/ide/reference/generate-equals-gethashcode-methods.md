---
title: Generovat C# Equals a GetHashCode – metoda přepsání
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d56a8f94665e20f8ca89b5a682eb6e44602bde0f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983739"
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-visual-studio"></a>Generování přepisů metod Equals a GetHashCode v sadě Visual Studio

Tato generace kód platí pro:

- C#

**Co:** Umožňuje generovat **rovná** a **GetHashCode** metody.

**Kdy:** Tato přepsání generovat, když máte typ, který by měly být porovnány pomocí jednoho nebo více polí, ne podle umístění objektu v paměti.

**Proč:**

- Při implementaci typu hodnoty, měli byste zvážit přepsání **rovná** metoda získat vyšší výkon nad výchozí implementace metody Equals na typ hodnoty.

- Pokud implementujete typem odkazu, měli byste zvážit přepsání **rovná** metodu, pokud váš typ vypadá jako základní typ, jako je například bod, řetězec, BigNumber a tak dále.

- Přepsat **GetHashCode** metoda umožňující typu fungovat správně v zatřiďovací tabulce. Přečtěte si informace o [operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators).

## <a name="how-to"></a>Postupy

1. Umístěte kurzor někam na řádek vaše deklaraci typu.

   ![Zvýrazněný kód](media/overrides-highlight-cs.png)

   > [!TIP]
   > Proveďte není dvojitým kliknutím vyberte název typu, nebo možnost nabídky nebude k dispozici. Právě umístěte kurzor někam na řádek.

1. Dále proveďte jednu z následujících akcí:

   - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.

   - Klikněte na ![šroubovák](../media/screwdriver-icon.png) ikona, která se zobrazí na levém okraji.

   ![Generovat přepsání ve verzi preview](media/overrides-preview-cs.png)

1. Vyberte **generovat Equals(objekt)** nebo **generovat Equals a GetHashCode** z rozevírací nabídky.

1. V **vyberte členy, kteří** dialogovém okně vyberte členy, které chcete generovat metody:

    ![Generovat přepsání dialogového okna](media/overrides-dialog-cs.png)

    > [!TIP]
    > Můžete také generovat operátory z tohoto dialogového okna pomocí zaškrtávacího políčka v dolní části dialogového okna.

   `Equals` a `GetHashCode` metody jsou generovány pomocí výchozí implementace.

   ![Generovat výsledek – metoda](media/overrides-result-cs.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)