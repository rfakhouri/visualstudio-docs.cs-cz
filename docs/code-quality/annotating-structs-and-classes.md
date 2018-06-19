---
title: Zadávání poznámek ke strukturám a třídám
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 076631860035e41451741d49843d9282ec4c15f7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31894345"
---
# <a name="annotating-structs-and-classes"></a>Zadávání poznámek ke strukturám a třídám
Členové struktury a třída může opatřit poznámkami pomocí poznámky, které fungují jako výstupních podmínek – nich předpokládá, že se na všechny volání funkce nebo funkce vstupu a výstupu, který zahrnuje nadřazených struktura jako parametr nebo výsledek hodnotu true.

## <a name="struct-and-class-annotations"></a>Struktura a poznámky – třída

-   `_Field_range_(low, high)`

     Toto pole je v rozsahu (včetně) z `low` k `high`.  Ekvivalentní `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` poznámkami objekt použít, a to pomocí vhodných podmínek před nebo po.

-   `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     Pole s velikostí zapisovatelné elementy (nebo bajtů) jako určeného `size`.

-   `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     Pole s velikostí zapisovatelné elementy (nebo bajtů) jako určeného `size`a `count` elementů (v bajtech), které jsou čitelné.

-   `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     Pole, která má parametr readable i writable velikost elementů (nebo bajtů) jako určeného `size`.

-   `_Struct_size_bytes_(size)`

     Pole, která má parametr readable i writable velikost elementů (nebo bajtů) jako určeného `size`.

     Platí pro třídy nebo struktury deklarace.  Označuje, že se počet bajtů ve specifikované může být větší než deklarovaný typ platný objekt daného typu `size`.  Příklad:

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     Velikost vyrovnávací paměti v bajtech parametru `pM` typu `MyStruct *` je nutno jako:

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="see-also"></a>Viz také
 [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md) [porozumění SAL](../code-quality/understanding-sal.md) [zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md) [zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md) [Zadávání poznámek k chování při zamykání](../code-quality/annotating-locking-behavior.md) [určující, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md) [vnitřní funkce](../code-quality/intrinsic-functions.md) [osvědčené postupy a Příklady](../code-quality/best-practices-and-examples-sal.md)