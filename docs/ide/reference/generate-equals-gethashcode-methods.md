---
title: Generování přepisů metod jazyka C# Equals a GetHashCode v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: deaa0b37988e2df04bb7937c76f341af849698f0
ms.sourcegitcommit: aea5cdb76fbc7eb31d1e5cc3c8d6adb0c743220f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/07/2018
ms.locfileid: "44124967"
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-visual-studio"></a>Generování přepisů metod Equals a GetHashCode v sadě Visual Studio

Tato generace kód platí pro:

- C#

**Co:** umožňuje generovat **rovná** a **GetHashCode** metody.

**Kdy:** generovat tato přepsání, když máte typ, který by měly být porovnány pomocí jednoho nebo více polí, ne podle umístění objektu v paměti.

**Proč:**

- Při implementaci typu hodnoty, měli byste zvážit přepsání **rovná** metoda získat vyšší výkon nad výchozí implementace metody Equals na typ hodnoty.

- Pokud implementujete typem odkazu, měli byste zvážit přepsání **rovná** metodu, pokud váš typ vypadá jako základní typ, jako je například bod, řetězec, BigNumber a tak dále.

- Přepsat **GetHashCode** metoda umožňující typu fungovat správně v zatřiďovací tabulce. Přečtěte si informace o [operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators).

## <a name="how-to"></a>Postupy

1. Umístěte kurzor vaše deklaraci typu.

   ![Zvýrazněný kód](media/overrides-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
     - Klikněte na ![Žárovka](media/bulb-cs.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na řádek s deklaraci typu.

   ![Generovat přepsání ve verzi preview](media/overrides-preview-cs.png)

1. Vyberte **generovat Equals(objekt)** nebo **generovat Equals a GetHashCode** z rozevírací nabídky.

1. V **vyberte členy, kteří** dialogovém okně vyberte členy, které chcete generovat metody:

    ![Generovat přepsání dialogového okna](media/overrides-dialog-cs.png)

    > [!TIP]
    > Můžete také generovat operátory z tohoto dialogového okna pomocí zaškrtávacích políček pod seznam členů.

   Equals a GetHashCode přepsání jsou generovány pomocí výchozí implementace.

   ![Generovat výsledek – metoda](media/overrides-result-cs.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)