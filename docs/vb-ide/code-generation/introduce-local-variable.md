---
title: "Zavést místní proměnné – generování kódu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1490d6ac-ed56-4d03-95db-c23f23cba70d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67302893dbebb65316b9c2aab09f70ddaa3e6567
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="introduce-a-local-variable-in-visual-basic"></a>Zavést místní proměnné v jazyce Visual Basic
**Co:** umožňuje okamžitě Generovat místní proměnné nahradit existující výrazu.

**Kdy:** máte kód, který by mohl snadno znovu použít později by měla v místní proměnné.  

**Důvod:** může zkopírujte a vložte kód vícekrát pro použití v různých umístěních, ale je lepší jednou operaci provést, uložit výsledek v místní proměnné a použít místní proměnné throughought. 

**Postupy:**

1. Zvýrazněte výraz, který chcete přiřadit k nové místní proměnné.

   ![Zvýrazněný kód](media/local_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte  **zavést místní (všech výskytů) se*výraz*' ** z místní okno náhledu, kde *výraz* je mít vámi vybraný úsek zvýrazněný kód.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte  **zavést místní (všech výskytů) se*výraz*' ** z místní okno náhledu, kde *výraz* je mít vámi vybraný úsek zvýrazněný kód.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Zavést místní náhled](media/local_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Místní proměnná bude automaticky vytvořen s typem odvodit z jeho použití.  Zadejte nový název nové místní proměnné zadáním.

   ![Zavést místní výsledek](media/local_result.png)

   >[!NOTE]
   >Můžete použít **.. nástroji výskyty...**  nabídky možnost nahraďte všechny výskyty vybraného výrazu najde, ne jenom jeden konkrétně zdůraznily.

## <a name="see-also"></a>Viz také  
[Generování kódu (Visual Basic)](../code-generation-vb.md)  
[Zobrazení náhledu změn](../../ide/preview-changes.md) 