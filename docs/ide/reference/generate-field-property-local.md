---
title: "Generovat pole, vlastnost nebo místní proměnné v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 8de048928286017d4e6f79bda6aff804b49d3150
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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
     - Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

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

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)
