---
title: "Generovat dokumentační komentáře XML - generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: b0a0ec1db54f57e14ddd412248f7a396336fe009
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="generate-xml-documentation-comments-in-c"></a>Generovat dokumentační komentáře XML v jazyce C# #
**Co:** umožňuje okamžitě generovat základní XML potřeba dokumentu vybraný prvek. 

**Kdy:** chcete vytvořit pro pozdější zpracování podle dokumentace nástroje, například aplikaci Sandcastle komentářů k dokumentu XML.

**Důvod:** můžete ručně vytvořit blok komentáře celý sami, ale tato akce ušetřit čas a zvyšte tak přesnost vygenerováním základní šablony a další prvky. 

**Postupy:**

1. Umístěte kurzor text nad elementem chcete dokumentů, například metodu.

   ![Metoda do dokumentu.](media/doc-highlight-cs.png)

1. Potom zadejte  **///**  (3 dál lomítka), který se automaticky vytvoří základní šablony a žádné další prvky podle potřeby.  Například při psaní komentářů metodu, vygeneruje  **\<souhrnné\>**  značky a také  **\<param\>**  značky pro každý parametr, který je předaný metodě a  **\<vrátí\>**  značky k dokumentu, vrátí metoda.

   ![Šablony](media/doc-preview-cs.png)

1. Dokončení komentáře a přidání, že žádné další informace, které si myslíte, že je potřeba.

   ![Dokončené komentář](media/doc-result-cs.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Dokumentační komentáře XML (C# Průvodce programováním)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
