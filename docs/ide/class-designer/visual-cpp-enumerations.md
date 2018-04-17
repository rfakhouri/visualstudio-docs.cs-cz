---
title: Výčty jazyka Visual C++ v Návrháři tříd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ac804f35c2d917e5443e61d4f2e53cde81165070
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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