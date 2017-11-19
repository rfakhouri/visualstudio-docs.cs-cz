---
title: "Struktury jazyka Visual C++ v Návrháři tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 85e2068e00f2164b44feb9aae61a47de426be735
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-structures-in-class-designer"></a>Struktury jazyka Visual C++ v návrháři tříd
Návrhář tříd podporuje C++ struktury, které jsou deklarovány s klíčovým slovem `struct`. Tady je příklad:  
  
```  
struct MyStructure  
{  
   char a;  
   int i;  
   long j;  
};  
```  
  
 Další informace o používání `struct` zadejte najdete v tématu [struktura](/cpp/cpp/struct-cpp).  
  
 Struktura obrazce C++ v diagramu tříd vypadat a fungovat jako obrazec třídy s tím rozdílem, že načte popisek **struktura** a má hranatými rohy místo zaoblenými hranami.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`struct StructureName {};`|**%{Structurename/**<br /><br /> Struktura|  
  
## <a name="see-also"></a>Viz také  
 [Práce s kódem jazyka Visual C++ (návrhář tříd)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Třídy a struktury](/cpp/cpp/classes-and-structs-cpp)   
 [Struktura](/cpp/cpp/struct-cpp)