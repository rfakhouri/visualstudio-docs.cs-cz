---
title: "Typ přesunout do odpovídající soubor - refaktoringu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 510b984ad2de9476d53e9a5a4bcd667f393d3d4b
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="move-type-to-a-matching-file-in-visual-basic"></a>Přesunutí typ, který má odpovídající soubor v jazyku Visual Basic

**Co:** umožňuje přesunout vybraný typ do samostatného souboru se stejným názvem.

**Kdy:** máte ve stejném souboru, který chcete použít k oddělení více tříd, struktur, rozhraní, atd.  

**Důvod:** umístění více typů ve stejném souboru může být obtížné vyhledat tyto typy.  Přesunutím typy souborů se stejným názvem bude kód čitelnější a snadný přechod.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název typu pro přesun:

   ![Zvýrazněný kód](media/movetype-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*VB** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*VB** z místní okno náhledu, kde  *TypeName* je název typu, který jste vybrali.

   Typ bude okamžitě přesunout na nový soubor s tímto názvem v rámci vašeho řešení.

   ![Vložené výsledek](media/movetype-result-vb.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)