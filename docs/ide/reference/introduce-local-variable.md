---
title: Zavést místní proměnné v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b7af958e923c6af7929b8e4a9309c210dbf8ced5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>Zavést místní proměnné v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě Generovat místní proměnné nahradit existující výrazu.

**Kdy:** máte kód, který by mohl snadno znovu použít později by měla v místní proměnné.

**Důvod:** může zkopírujte a vložte kód vícekrát pro použití v různých umístěních, ale je lepší jednou operaci provést, uložit výsledek v místní proměnné a použít místní proměnné throughought.

## <a name="how-to"></a>Postupy

1. Zvýrazněte výraz, který chcete přiřadit k nové místní proměnné.

   - C#:

    ![Zvýrazněný kód C#](media/local-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/local-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Zavést místní náhled](media/local-preview-cs.png)

1. Vyberte **zavést místní (všech výskytů):*výraz*'** z rozevírací nabídky.

   > [!TIP]
   > Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.

   Vytvořen, místní proměnné s typem odvodit z jeho použití. Zadejte nový název nové místní proměnné.

   - C#:

      ![Implementace rozhraní výsledek C#](media/local-result-cs.png)

   - Visual Basic:

      ![Implementace rozhraní výsledek jazyka Visual Basic](media/local-result-vb.png)

   > [!NOTE]
   > Můžete použít **.. nástroji výskyty...**  nabídky možnost nahraďte všechny výskyty vybraného výrazu, ne jenom jeden konkrétně zdůraznily.

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
