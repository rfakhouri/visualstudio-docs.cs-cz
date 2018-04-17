---
title: Generovat pole, vlastnost nebo místní proměnné v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: c42a1b22a7ae191fe9024e45df66695d10f102e8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="generate-a-field-property-or-local-variable-in-visual-studio"></a>Generovat pole, vlastnost nebo místní proměnné v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu pro dříve nedeklarované pole, vlastnost nebo místní.

**Kdy:** zavést nové pole, vlastnost nebo místní během psaní a chcete správně, automaticky deklarovat.

**Důvod:** pole, vlastnost nebo místní může deklarovat před použitím, ale tato funkce bude generovat deklaraci a zadejte automaticky.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou. Červenou vlnovkou určuje pole, místní nebo vlastnost, která ještě neexistuje.

   - C#:

    ![Zvýrazněný kód C#](media/field-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/field-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

    ![Vytvoření náhledu pole nebo vlastnost nebo místní](media/field-preview-cs.png)

1. Vyberte jednu z možností generování z rozevírací nabídky.

   > [!TIP]
   > Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.

   Pole, vlastnost nebo místní je vytvořen s typem odvodit z jeho použití.

   - C#:

      ![Generovat výsledek metody C#](media/field-result-cs.png)

   - Visual Basic:

      ![Generovat výsledek metody jazyka Visual Basic](media/field-result-vb.png)

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
