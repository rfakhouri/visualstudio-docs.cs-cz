---
title: "Typ přesunout do odpovídající soubor - refaktoringu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8e0b3fd-d1d9-4e3f-b0f6-9f8ffbbc6297
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6b5d42bf01f8979cb52ea4fb4f89f16a78d78024
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="move-type-to-a-matching-file-in-visual-basic"></a>Přesunutí typ, který má odpovídající soubor v jazyku Visual Basic
**Co:** umožňuje přesunout vybraný typ do samostatného souboru se stejným názvem.

**Kdy:** máte ve stejném souboru, který chcete použít k oddělení více tříd, struktur, rozhraní, atd.  

**Důvod:** umístění více typů ve stejném souboru může být obtížné vyhledat tyto typy.  Přesunutím typy souborů se stejným názvem bude kód čitelnější a snadný přechod.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název typu pro přesun:

   ![Zvýrazněný kód](media/movetype_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*VB** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **přesunout typ *TypeName*VB** z místní okno náhledu, kde  *TypeName* je název typu, který jste vybrali.

   Typ bude okamžitě přesunout na nový soubor s tímto názvem v rámci vašeho řešení.

   ![Vložené výsledek](media/movetype_result.png)

## <a name="see-also"></a>Viz také
[Refaktoringu (Visual Basic)](../refactoring-vb.md)