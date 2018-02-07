---
title: "Zavést místní proměnné – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6ba9478c09e55df54f94ed93c7a694f798ae76b4
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="introduce-a-local-variable-in-c"></a>Zavést místní proměnné v jazyce C# #

**Co:** umožňuje okamžitě Generovat místní proměnné nahradit existující výrazu.

**Kdy:** máte kód, který by mohl snadno znovu použít později by měla v místní proměnné.

**Důvod:** může zkopírujte a vložte kód vícekrát pro použití v různých umístěních, ale je lepší jednou operaci provést, uložit výsledek v místní proměnné a použít místní proměnné throughought.

**Postupy:**

1. Zvýrazněte výraz, který chcete přiřadit k nové místní proměnné.

   ![Zvýrazněný kód](media/local-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **zavést místní (všech výskytů) se*výraz*'** z místní okno náhledu, kde *výraz* je mít vámi vybraný úsek zvýrazněný kód.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **zavést místní (všech výskytů) se*výraz*'** z místní okno náhledu, kde *výraz* je mít vámi vybraný úsek zvýrazněný kód.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Zavést místní náhled](media/local-preview-cs.png)

   > [!TIP]
   > Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Místní proměnná bude automaticky vytvořen s typem odvodit z jeho použití.  Zadejte nový název nové místní proměnné zadáním.

   ![Zavést místní výsledek](media/local-result-cs.png)

   > [!NOTE]
   > Můžete použít **.. nástroji výskyty...**  nabídky možnost nahraďte všechny výskyty vybraného výrazu najde, ne jenom jeden konkrétně zdůraznily.

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)
