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
ms.workload: cplusplus
ms.openlocfilehash: d6f2aa3893a230abd52dd5cf19ed9d751e56e50c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="visual-c-structures-in-class-designer"></a>Struktury jazyka Visual C++ v návrháři tříd
Návrhář tříd podporuje C++ struktury, které jsou deklarovány s klíčovým slovem `struct`. Tady je příklad:  
  
```cpp
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
[Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)   
[Třídy a struktury](/cpp/cpp/classes-and-structs-cpp)   
[struct](/cpp/cpp/struct-cpp)