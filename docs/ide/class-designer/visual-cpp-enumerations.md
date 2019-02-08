---
title: Výčty jazyka Visual C++ v návrháři tříd
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: f31f153183d0cdd809bd9dde9187ade32b20ddd2
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939850"
---
# <a name="visual-c-enumerations-in-class-designer"></a>Výčty Visual C++ v Návrháři tříd

**Návrhář tříd** podporuje C++ `enum` a s vymezeným oborem `enum class` typy. Tady je příklad:

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

Tvar výčtu C++ v diagramu třídy vypadá a funguje jako tvar struktury, s tím rozdílem, že načte popisek **výčtu** nebo **Enum class**, je růžový místo modrý a má barevné ohraničení na levém a horním okraje. Obrazce výčtu i obrazce struktury mají hranaté rohy.

Další informace o používání `enum` zadejte naleznete v tématu [výčty](/cpp/cpp/enumerations-cpp).

## <a name="see-also"></a>Viz také:

- [Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)
- [Výčty](/cpp/cpp/enumerations-cpp)