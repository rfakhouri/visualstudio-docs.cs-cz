---
title: Přidání místní proměnné v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: d028d89f149a2fe444508d09086f6bec2408889e
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2018
ms.locfileid: "39510998"
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>Přidání místní proměnné v sadě Visual Studio

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě Generovat lokální proměnná má nahradit stávající výraz.

**Kdy:** budete mít kód, který se dá snadno opakovaně použít později byl v místní proměnné.

**Důvod, proč:** může zkopírujte a vložte kód několikrát jeho použití v různých umístěních, ale bylo by lepší provést operaci jednou, uloží výsledek v místní proměnné a používat místní proměnné v rámci.

## <a name="how-to"></a>Postupy

1. Zvýrazněte výraz, který chcete přiřadit nový místní proměnné.

   - C#:

    ![Zvýrazněný kód jazyka C#](media/local-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/local-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
     - Klikněte na ![Žárovka](media/bulb-cs.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na řádek s červená vlnovka.

   ![Zavést místní náhled](media/local-preview-cs.png)

1. Vyberte **zavést místní pro (všechny výskyty) "*výraz*"** z rozevírací nabídky.

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