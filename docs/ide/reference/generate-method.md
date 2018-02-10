---
title: "Generovat metody v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6fbee2d6ea0a6d95d6d71114dc116cfaa1ede74e
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="generate-a-method-in-visual-studio"></a>Generovat metody v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě přidání metody do třídy.

**Kdy:** zavést nové metody a chcete správně, automaticky deklarovat.

**Důvod:** je může deklarovat metodu a parametry před použitím, ale tato funkce bude automaticky generovat deklaraci.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou. Červenou vlnovkou označuje metodu, která ještě neexistuje.

   - C#:

    ![Zvýrazněný kód C#](media/method-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/method-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

    ![Vytvoření náhledu – metoda](media/method-preview-cs.png)

1. Vyberte **generovat metoda** z rozevírací nabídky.

   > [!TIP]
   > Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.

   Metoda je vytvořen s parametry odvodit z jeho použití.

   - C#:

      ![Generovat výsledek metody C#](media/method-result-cs.png)

   - Visual Basic:

      ![Generovat výsledek metody jazyka Visual Basic](media/method-result-vb.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)
