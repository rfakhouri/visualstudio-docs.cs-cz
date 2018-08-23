---
title: Výčty jazyka Visual C++ v Návrháři tříd | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6d4bc1385c934d9858cef19f8ffe73ad6a0baaf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696426"
---
# <a name="visual-c-enumerations-in-class-designer"></a>Výčty jazyka Visual C++ v návrháři tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [výčty Visual C++ v Návrháři tříd](https://docs.microsoft.com/visualstudio/ide/visual-cpp-enumerations-in-class-designer).  
  
Návrhář tříd podporuje C++ `enum` a s vymezeným oborem `enum class` typy. Tady je příklad:  
  
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
  
 Tvar výčtu C++ v diagramu třídy vypadá a funguje jako tvar struktury, s tím rozdílem, že načte popisek **výčtu** nebo **Enum class**, je růžový místo modrý a má barevné ohraničení na levém a horním okraje. Obrazce výčtu i obrazce struktury mají hranaté rohy.  
  
 Další informace o používání `enum` zadejte naleznete v tématu [výčty](http://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3).  
  
## <a name="see-also"></a>Viz také  
 [Práce s kódem jazyka Visual C++ (návrhář tříd)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Výčty](http://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3)



