---
title: Zadávání poznámek ke strukturám a třídám
ms.date: 06/28/2019
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
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 35be465064c9524eb0e1339794b6a19b7a595da1
ms.sourcegitcommit: d2b234e0a4a875c3cba09321cdf246842670d872
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2019
ms.locfileid: "67493639"
---
# <a name="annotating-structs-and-classes"></a>Zadávání poznámek ke strukturám a třídám

Členy struktury a třídy může opatřit poznámkami pomocí poznámek, které fungují jako výstupních podmínek, jsou považovány za na hodnotu true v jakékoli volání funkce nebo funkce zahájení/ukončení, která zahrnuje ohraničující struktuře jako parametr nebo je výsledná hodnota.

## <a name="struct-and-class-annotations"></a>Struktury a třídy poznámky

- `_Field_range_(low, high)`

     Pole je v rozsahu (včetně) z `low` k `high`.  Ekvivalentní `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` u objektu s poznámkami pomocí vhodných podmínek před nebo po.

- `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     Pole, které má zapisovatelná velikost elementů (nebo bajtů) jako určené `size`.

- `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     Pole, které má zapisovatelná velikost elementů (nebo bajtů) jako určené `size`a `count` elementů (v bajtech), které čitelné.

- `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     Pole, které má parametr readable i writable velikost elementů (nebo bajtů) jako určené `size`.

- `_Field_z_`

     Pole, které obsahuje řetězec zakončený hodnotou null.

- `_Struct_size_bytes_(size)`

     Platí pro deklaraci třídy nebo struktury.  Označuje, že platný objekt daného typu může být větší než deklarovaného typu, s počtem bajtů se určené `size`.  Příklad:

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     Velikost vyrovnávací paměti v bajtech parametr `pM` typu `MyStruct *` pak slov za:

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="example"></a>Příklad

```cpp
#include <sal.h>
// For FIELD_OFFSET macro
#include <windows.h>

// This _Struct_size_bytes_ is equivalent to what below _Field_size_ means.
_Struct_size_bytes_(FIELD_OFFSET(MyBuffer, buffer) + bufferSize * sizeof(int))
struct MyBuffer
{
    static int MaxBufferSize;
    
    _Field_z_
    const char* name;
    
    int firstField;

    // ... other fields

    _Field_range_(1, MaxBufferSize)
    int bufferSize;
    _Field_size_(bufferSize)        // Prefered way - easier to read and maintain.
    int buffer[0];
};
```

Poznámky v tomto příkladu:

- `_Field_z_` je ekvivalentní `_Null_terminated_`.  `_Field_z_` Název pole určuje, že pole název je řetězec zakončený hodnotou null.
- `_Field_range_` pro `bufferSize` Určuje, že hodnota `bufferSize` by měla být v rámci 1 a `MaxBufferSize` (obojí včetně).
- Výsledky end `_Struct_size_bytes_` a `_Field_size_` poznámky jsou ekvivalentní. Pro struktury nebo třídy, které mají podobné rozložení `_Field_size_` je snadněji čte i údržbu, protože má menší počet odkazů a výpočty, než ekvivalentní `_Struct_size_bytes_` poznámky. `_Field_size_` nevyžaduje převod na velikost v bajtech. Pokud velikost v bajtech je jedinou možností, například pro pole ukazatelů void, `_Field_size_bytes_` lze použít. Pokud mají oba `_Struct_size_bytes_` a `_Field_size_` neexistuje, jak budou mít k dispozici nástroje. Je nástroj pro co dělat, když dva poznámky Nesouhlasím.

## <a name="see-also"></a>Viz také

- [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Porozumění SAL](../code-quality/understanding-sal.md)
- [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)
- [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)
- [Zadávání poznámek o chování při zamykání](../code-quality/annotating-locking-behavior.md)
- [Určení, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Vnitřní funkce](../code-quality/intrinsic-functions.md)
- [Doporučené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)