---
title: Zadávání poznámek ke strukturám a třídám | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 11
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f3d20769215058cca6e30955ae37ad2a78b6bc7c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49287453"
---
# <a name="annotating-structs-and-classes"></a>Zadávání poznámek ke strukturám a třídám
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Členy struktury a třídy může opatřit poznámkami pomocí poznámek, které fungují jako výstupních podmínek, jsou považovány za na hodnotu true v jakékoli volání funkce nebo funkce zahájení/ukončení, která zahrnuje ohraničující struktuře jako parametr nebo je výsledná hodnota.  
  
## <a name="struct-and-class-annotations"></a>Struktury a třídy poznámky  
  
-   `_Field_range_(low, high)`  
  
     Pole je v rozsahu (včetně) z `low` k `high`.  Ekvivalentní `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` u objektu s poznámkami pomocí vhodných podmínek před nebo po.  
  
-   `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`  
  
     Pole, které má zapisovatelná velikost elementů (nebo bajtů) jako určené `size`.  
  
-   `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`  
  
     Pole, které má zapisovatelná velikost elementů (nebo bajtů) jako určené `size`a `count` elementů (v bajtech), které čitelné.  
  
-   `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`  
  
     Pole, které má parametr readable i writable velikost elementů (nebo bajtů) jako určené `size`.  
  
-   `_Struct_size_bytes_(size)`  
  
     Pole, které má parametr readable i writable velikost elementů (nebo bajtů) jako určené `size`.  
  
     Platí pro deklaraci třídy nebo struktury.  Označuje, že platný objekt daného typu může být větší než deklarovaného typu, s počtem bajtů se určené `size`.  Příklad:  
  
    ```cpp  
  
    typedef _Struct_size_bytes_(nSize)  
    struct MyStruct {  
        size_t nSize;  
        …  
    };  
  
    ```  
  
     Velikost vyrovnávací paměti v bajtech parametr `pM` typu `MyStruct *` pak slov za:  
  
    ```cpp  
    min(pM->nSize, sizeof(MyStruct))  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Použití poznámek SAL k omezení defektů kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [Porozumění SAL](../code-quality/understanding-sal.md)   
 [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)   
 [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)   
 [Zadávání poznámek o chování při zamykání](../code-quality/annotating-locking-behavior.md)   
 [Určení, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [Vnitřní funkce](../code-quality/intrinsic-functions.md)   
 [Doporučené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)



