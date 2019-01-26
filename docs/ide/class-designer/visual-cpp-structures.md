---
title: Struktury jazyka Visual C++ v návrháři tříd
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 6daa85e9f8a3ea6f5fe68808cd46fc4414f77c17
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54966358"
---
# <a name="visual-c-structures-in-class-designer"></a>Struktury Visual C++ v Návrháři tříd

**Návrhář tříd** podporuje struktury, C++, které jsou deklarovány pomocí klíčového slova `struct`. Tady je příklad:

```cpp
struct MyStructure
{
   char a;
   int i;
   long j;
};
```

Další informace o používání `struct` zadejte naleznete v tématu [struktura](/cpp/cpp/struct-cpp).

Tvar struktury C++ v diagramu třídy vypadá a funguje jako tvar třídy, s tím rozdílem, že načte popisek **struktura** a má hranaté rohy místo zaoblené rohy.

|Element kódu|Zobrazení návrháře tříd|
|------------------| - |
|`struct StructureName {};`|**%{Structurename/**<br /><br /> Struktura|

## <a name="see-also"></a>Viz také:

- [Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)
- [Třídy a struktury](/cpp/cpp/classes-and-structs-cpp)
- [struct](/cpp/cpp/struct-cpp)