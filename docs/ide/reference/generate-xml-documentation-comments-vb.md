---
title: "Generovat dokumentační komentáře XML v jazyce Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2f421553657dfafb265140e44e38a2c7722a7303
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>Generovat dokumentační komentáře XML v jazyce Visual Basic

**Co:** umožňuje okamžitě generovat základní XML potřeba dokumentu vybraný prvek. 

**Kdy:** chcete vytvořit pro pozdější zpracování podle dokumentace nástroje, například aplikaci Sandcastle komentářů k dokumentu XML.

**Důvod:** můžete ručně vytvořit blok komentáře celý sami, ale tato akce ušetřit čas a zvyšte tak přesnost vygenerováním základní šablony a další prvky. 

**Postupy:**

1. Umístěte kurzor text nad elementem chcete dokumentů, například metodu.

   ![Metoda do dokumentu.](media/doc-highlight-vb.png)

1. Potom zadejte **'''** (3 jednoduchých uvozovkách) který automaticky vytvoří základní šablony a žádné další prvky podle potřeby.  Například při psaní komentářů metodu, vygeneruje  **\<souhrnné\>**  značky a také  **\<param\>**  značky pro každý parametr, který je předaný metodě a  **\<vrátí\>**  značky k dokumentu, vrátí metoda.

   ![Šablony](media/doc-preview-vb.png)

1. Dokončení komentáře a přidání, že žádné další informace, které si myslíte, že je potřeba.

   ![Dokončené komentář](media/doc-result-vb.png)

## <a name="see-also"></a>Viz také

[Dokumentace kódu s XML (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[Generování kódu](../code-generation-in-visual-studio.md)