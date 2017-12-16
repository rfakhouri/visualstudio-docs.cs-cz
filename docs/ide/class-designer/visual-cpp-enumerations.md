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
ms.openlocfilehash: f7f5ccb0bedd57b6b72d06e39e8829aa9d6b140d
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="visual-c-enumerations-in-class-designer"></a>Výčty jazyka Visual C++ v návrháři tříd
Návrhář tříd podporuje C++ `enum` a oboru `enum class` typy. Tady je příklad:  
  
```cpp
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
[Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)   
[Výčty](/cpp/cpp/enumerations-cpp)