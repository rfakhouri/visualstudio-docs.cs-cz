---
title: "Výčty jazyka Visual C++ v Návrháři tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5cbe3616fa81218c7fbfba31f55d241c3e45dacc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-enumerations-in-class-designer"></a>Výčty jazyka Visual C++ v návrháři tříd
Návrhář tříd podporuje C++ `enum` a oboru `enum class` typy. Tady je příklad:  
  
```  
enum CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
// or...  
enum class CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
```  
  
 C++ – výčet obrazce v diagramu tříd vypadat a fungovat jako struktura obrazce, s výjimkou toho, aby četl popisek **výčtu** nebo **výčet tříd**, je růžový místo blue a má barevný vlevo a horní okraj okraje. Výčet tvarů a struktura tvarů mít hranatými rohy.  
  
 Další informace o používání `enum` zadejte najdete v tématu [výčty](/cpp/cpp/enumerations-cpp).  
  
## <a name="see-also"></a>Viz také  
 [Práce s kódem jazyka Visual C++ (návrhář tříd)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Výčty](/cpp/cpp/enumerations-cpp)