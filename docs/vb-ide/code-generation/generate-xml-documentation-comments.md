---
title: "Generovat dokumentační komentáře XML - generování kódu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f975fa077fe64052b54875b07d029ece71e83372
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>Generovat dokumentační komentáře XML v jazyce Visual Basic
**Co:** umožňuje okamžitě generovat základní XML potřeba dokumentu vybraný prvek. 

**Kdy:** chcete vytvořit pro pozdější zpracování podle dokumentace nástroje, například aplikaci Sandcastle komentářů k dokumentu XML.

**Důvod:** můžete ručně vytvořit blok komentáře celý sami, ale tato akce ušetřit čas a zvyšte tak přesnost vygenerováním základní šablony a další prvky. 

**Postupy:**

1. Umístěte kurzor text nad elementem chcete dokumentů, například metodu.

   ![Metoda do dokumentu.](media/doc_highlight.png)

1. Potom zadejte **'''** (3 jednoduchých uvozovkách) který automaticky vytvoří základní šablony a žádné další prvky podle potřeby.  Například při psaní komentářů metodu, vygeneruje  **\<souhrnné\>**  značky a také  **\<param\>**  značky pro každý parametr, který je předaný metodě a  **\<vrátí\>**  značky k dokumentu, vrátí metoda.

   ![Šablony](media/doc_preview.png)

1. Dokončení komentáře a přidání, že žádné další informace, které si myslíte, že je potřeba.

   ![Dokončené komentář](media/doc_result.png)

## <a name="see-also"></a>Viz také
[Dokumentace kódu s XML (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[Generování kódu (Visual Basic)](../code-generation-vb.md) 