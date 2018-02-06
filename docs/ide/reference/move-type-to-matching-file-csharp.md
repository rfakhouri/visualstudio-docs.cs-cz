---
title: "Typ přesunout do odpovídající soubor - refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 4b7b9b1ba52bed5d2bdf042db0149d799c489a7d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>Přesunout typu do odpovídající soubor v jazyku C# #

**Co:** umožňuje přesunout vybraný typ do samostatného souboru se stejným názvem.

**Kdy:** máte ve stejném souboru, který chcete použít k oddělení více tříd, struktur, rozhraní, atd.

**Důvod:** umístění více typů ve stejném souboru může být obtížné vyhledat tyto typy.  Přesunutím typy souborů se stejným názvem bude kód čitelnější a snadný přechod.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název typu pro přesun:

   ![Zvýrazněný kód](media/movetype-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*.cs** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*.cs** z místní okno náhledu, kde  *TypeName* je název typu, který jste vybrali.

   Typ bude okamžitě přesunout na nový soubor s tímto názvem v rámci vašeho řešení.

   ![Vložené výsledek](media/movetype-result-cs.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)