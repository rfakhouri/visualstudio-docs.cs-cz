---
title: Generovat pole, vlastnost nebo místní proměnné v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 60472c83738351ebc46a96e9d53bc4ae3015c514
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2018
ms.locfileid: "51296226"
---
# <a name="generate-a-field-property-or-local-variable-in-visual-studio"></a>Generovat pole, vlastnost nebo místní proměnné v sadě Visual Studio

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu pro dříve nedeklarovaný pole, vlastnost nebo místní.

**Kdy:** představují nové pole, vlastnosti nebo místní při psaní a chcete správně, automaticky deklarovat.

**Důvod, proč:** můžete deklarovat pole, vlastnost nebo místní než ho začnete využívat, ale tato funkce bude generovat deklarace a zadejte automaticky.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází červená vlnovka. Červená vlnovka určuje pole, místní nebo vlastnost, která ještě neexistuje.

   - C#:

       ![Zvýrazněný kód jazyka C#](media/field-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód jazyka Visual Basic](media/field-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Červená vlnovka ukazatel myši a klikněte ![Žárovka](media/bulb-cs.png) ikona, která se zobrazí.
      - Klikněte na ![Žárovka](media/bulb-cs.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na řádek s červená vlnovka.

      ![Generování pole/vlastnosti/místní funkce ve verzi preview](media/field-preview-cs.png)

3. Vyberte jednu z generování možností z rozevírací nabídky.

   > [!TIP]
   > Použití **náhled změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , který bude proveden před zvolení požadované možnosti.

   Pole, vlastnost nebo místní se vytvoří s typem odvodit z jeho využití.

   - C#:

       ![Generovat výsledek metody jazyka C#](media/field-result-cs.png)

   - Visual Basic:

       ![Generovat výsledek metody VB](media/field-result-vb.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)