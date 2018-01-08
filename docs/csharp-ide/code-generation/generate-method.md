---
title: "Generate – metoda – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683790b4-b68b-42d7-8dc4-a68eca05aa01
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 2d0354549d01fb31a813630066c96f6378db4b7a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-method-in-c"></a>Generovat metody v jazyce C# #
**Co:** umožňuje okamžitě přidání metody do třídy. 

**Kdy:** zavést nové metody a chcete správně, automaticky deklarovat.  

**Důvod:** je může deklarovat metodu a parametry před použitím, ale tato funkce bude automaticky generovat deklaraci. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující použijete metodu, která ještě neexistuje.

   ![Zvýrazněný kód](media/method_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **generovat metoda** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **generovat metoda** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Vytvoření náhledu – metoda](media/method_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Metoda vytvoří se automaticky s parametry odvodit z jeho použití.

   ![Generování výsledků – metoda](media/method_result.png)

## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)
