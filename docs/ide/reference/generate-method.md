---
title: Generování metody
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d815b638033e16796c90a362207b820bfe7cc57d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62794811"
---
# <a name="generate-a-method-in-visual-studio"></a>Generovat metodu v sadě Visual Studio

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** Umožňuje okamžitě přidat metodu do třídy.

**Kdy:** Zavádí nové metody a chcete správně, automaticky deklarovat.

**Proč:** Můžete deklarovat metody a parametrů než začnete používat, ale tato funkce bude automaticky generovat deklarace.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází červená vlnovka. Červená vlnovka označuje metodu, která ještě neexistuje.

   - C#:

       ![Zvýrazněný kód jazyka C#](media/method-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód jazyka Visual Basic](media/method-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Červená vlnovka ukazatel myši a klikněte ![Chyba žárovky](media/error-bulb.png) ikona, která se zobrazí.
      - Klikněte na ![Chyba žárovky](media/error-bulb.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na řádek s červená vlnovka.

      ![Vytvoření náhledu – metoda](media/method-preview-cs.png)

3. Vyberte **generovat metodu** z rozevírací nabídky.

   > [!TIP]
   > Použití **náhled změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , který bude proveden před zvolení požadované možnosti.

   Metoda se vytvoří s parametry odvodit z jeho využití.

   - C#:

       ![Generovat výsledek metody jazyka C#](media/method-result-cs.png)

   - Visual Basic:

       ![Generovat výsledek metody VB](media/method-result-vb.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)