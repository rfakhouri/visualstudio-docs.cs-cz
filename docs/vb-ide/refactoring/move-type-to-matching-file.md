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
ms.workload: multiple
ms.openlocfilehash: 862c144c2319f6247a9fd38d7f71036a4ba090a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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