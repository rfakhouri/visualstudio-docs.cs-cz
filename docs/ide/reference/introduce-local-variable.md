---
title: Přidání místní proměnné
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 5564752fcecfe2d7a1b2d0bf7632a9cebe3d9353
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55921221"
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>Přidání místní proměnné v sadě Visual Studio

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** Umožňuje okamžitě Generovat lokální proměnná má nahradit stávající výraz.

**Kdy:** Máte kód, který se dá snadno opakovaně použít později byl v místní proměnné.

**Proč:** Může zkopírujte a vložte kód několikrát jeho použití v různých umístěních, ale bylo by lepší provést operaci jednou, uloží výsledek v místní proměnné a používat místní proměnné v rámci.

## <a name="how-to"></a>Postupy

1. Zvýrazněte výraz, který chcete přiřadit nový místní proměnné.

   - C#:

       ![Zvýrazněný kód jazyka C#](media/local-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód jazyka Visual Basic](media/local-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Klikněte na ![šroubovák](media/screwdriver.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na řádek zvýrazněný výrazem.

   ![Zavést místní náhled](media/local-preview-cs.png)

3. Vyberte **zavést lokální proměnnou (všech výskytů) "výrazu"** z rozevírací nabídky.

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