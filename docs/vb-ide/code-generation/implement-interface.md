---
title: "Implementace rozhraní – generování kódu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bebff2ad-25b6-4adc-8762-60d23bdd639a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4a8a6c2e5edf0acc7382a5099afbbe953ceae2a6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implement-an-interface-in-visual-basic"></a>Implementace rozhraní v jazyce Visual Basic
**Co:** umožňuje okamžitě generování kódu potřebnou k implementaci rozhraní. 

**Kdy:** chcete použít dědění z rozhraní.  

**Důvod:** může ručně implementovat všechny rozhraní jeden po druhém, ale tato funkce bude automaticky generovat všechny podpisy metoda. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující mít odkazuje rozhraní, ale ještě implementována všech požadovaných členů.

   ![Zvýrazněný kód](media/interface_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **implementovat rozhraní (explicitně)** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **implementovat rozhraní (explicitně)** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Implementace třídy preview](media/interface_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.
   >
   >Kromě toho můžete použít **dokumentu**, **projektu**, a **řešení** odkazy v dolní části okna náhledu k vytvoření podpisy správné metody napříč více třídy, které implementují rozhraní.

1. Podpisy metoda v rozhraní bude automaticky vytvořený, připraveno k implementaci.

   ![Implementace výsledek – třída](media/interface_result.png)

## <a name="see-also"></a>Viz také  
[Generování kódu (Visual Basic)](../code-generation-vb.md)  
[Náhled změn](../../ide/preview-changes.md)