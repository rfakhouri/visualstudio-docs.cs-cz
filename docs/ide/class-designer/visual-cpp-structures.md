---
title: Struktury jazyka Visual C++ v Návrháři tříd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: d0621b5a2a82786a41e8d566954f03341affa905
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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