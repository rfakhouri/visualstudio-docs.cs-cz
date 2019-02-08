---
title: Implementace rozhraní
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 58c714dec8b8a4679d34168cdaf901dc2fb94ea6
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55934273"
---
# <a name="implement-an-interface-in-visual-studio"></a>Implementovat rozhraní v sadě Visual Studio

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** Umožňuje okamžitě generovat kód potřebný k implementaci rozhraní.

**Kdy:** Chcete-li dědit z rozhraní.

**Proč:** Může ručně implementovat všechny rozhraní jeden po druhém, ale tato funkce automaticky vygeneruje všechny podpisy metod.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází červená vlnovka, která určuje neodkazujete rozhraní, ale neimplementovali všechny požadované členy.

   - C#:

       ![Zvýrazněný kód jazyka C#](media/interface-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód jazyka Visual Basic](media/interface-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Červená vlnovka ukazatel myši a klikněte ![Chyba žárovky](media/error-bulb.png) ikona, která se zobrazí.
      - Klikněte na ![Chyba žárovky](media/error-bulb.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na řádek s červená vlnovka.

3. Vyberte **implementovat rozhraní** z rozevírací nabídky.

   ![Implementovat rozhraní ve verzi preview](media/interface-preview-cs.png)

   > [!TIP]
   > - Použití **náhled změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , který bude proveden před zvolení požadované možnosti.
   > - Použití **dokumentu**, **projektu**, a **řešení** odkazy v dolní části okna ve verzi preview vytvořit správnou metodu podpisy v rámci více tříd, které implementují rozhraní.

   Podpisy metod rozhraní je vytvořen a připraven k implementaci.

   - C#:

       ![Implementovat rozhraní výsledek C#](media/interface-result-cs.png)

   - Visual Basic:

       ![Implementovat rozhraní výsledek VB](media/interface-result-vb.png)

   > [!TIP]
   > (C# jenom) Použití **implementovat rozhraní explicitně** možnost používaly každý vygeneruje metodu s názvem rozhraní, aby se zabránilo kolize názvů.
   >
   > ![Implementovat rozhraní explicitně způsobit.](media/interface-explicitresult-cs.png);

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)