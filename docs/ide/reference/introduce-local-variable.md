---
title: Přidání místní proměnné
description: Vygeneruje místní proměnnou, která nahradí existující výraz. Vyberte výraz, klikněte na něj pravým tlačítkem a vyberte nabídku rychlé akce a refaktoringy, vyberte zavést místní pro (všechny výskyty) výrazu.
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 43f54072d495cfdd6607ccb033ffd1a1713ad8bb
ms.sourcegitcommit: 0f5f7955076238742f2071d286ad8e896f3a6cad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68483687"
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>Přidání místní proměnné v sadě Visual Studio

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** Umožňuje ihned vygenerovat místní proměnnou, která nahradí existující výraz.

**Kdy:** Máte kód, který můžete později snadno znovu použít, pokud byl v místní proměnné.

**Proč:** Kód můžete zkopírovat a vložit několikrát, abyste ho mohli použít v různých umístěních, ale bylo by lepší provést operaci jednou, uložit výsledek do místní proměnné a použít místní proměnnou v rámci.

## <a name="how-to"></a>Postupy

1. Zvýrazněte výraz, který chcete přiřadit nový místní proměnné.

   - C#:

       ![Zvýrazněný kód jazyka C#](media/local-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód jazyka Visual Basic](media/local-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Klikněte na ![screwdriver](media/screwdriver.png) ikona, která se zobrazí na levém okraji, pokud je textový kurzor již na řádku se zvýrazněným výrazem.

   ![Zavést místní náhled](media/local-preview-cs.png)

3. Z rozevírací nabídky vyberte **zavést místní pro (všechny výskyty) výrazu** .

   > [!TIP]
   > Použití **náhled změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , který bude proveden před zvolení požadované možnosti.

   Místní proměnná se vytvoří s typem odvodit z jeho využití. Zadejte nový název nové místní proměnné.

   - C#:

       ![Implementovat rozhraní výsledek C#](media/local-result-cs.png)

   - Visual Basic:

       ![Implementovat rozhraní výsledek VB](media/local-result-vb.png)

   > [!NOTE]
   > Můžete použít **.. nástroji výskytů...**  nahraďte každý výskyt vybraného výrazu, ne jenom jeden konkrétně zdůraznily možnost nabídky.

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)