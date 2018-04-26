---
title: Struktury jazyka Visual C++ v návrháři tříd
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 36d9e78a1944817d9384d0c55b9584e58a758ccc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="visual-c-structures-in-class-designer"></a>Struktury Visual C++ v Návrháři tříd

**Třídy návrháře** podporuje C++ struktury, které jsou deklarovány s klíčovým slovem `struct`. Tady je příklad:

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

- [Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)
- [Třídy a struktury](/cpp/cpp/classes-and-structs-cpp)
- [struct](/cpp/cpp/struct-cpp)