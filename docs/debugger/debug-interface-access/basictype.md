---
title: Basictype – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03e82a8c17b33aa085b4ed64b9ba609bee183e1d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56626112"
---
# <a name="basictype"></a>BasicType
Určuje základní typ symbolu.

## <a name="syntax"></a>Syntaxe

```C++
enum BasicType {
    btNoType   = 0,
    btVoid     = 1,
    btChar     = 2,
    btWChar    = 3,
    btInt      = 6,
    btUInt     = 7,
    btFloat    = 8,
    btBCD      = 9,
    btBool     = 10,
    btLong     = 13,
    btULong    = 14,
    btCurrency = 25,
    btDate     = 26,
    btVariant  = 27,
    btComplex  = 28,
    btBit      = 29,
    btBSTR     = 30,
    btHresult  = 31,
    btChar16   = 32,  // char16_t
    btChar32   = 33,  // char32_t
};
```

## <a name="elements"></a>Elementy
btNoType, který není zadán žádný základní typ.

btVoid základní typ je `void`.

btChar základní typ je `char` (C/C++ typ).

btWChar základní typ je širokého znaku (Unicode) (`WCHAR`).

btInt základní typ je `signed int` (C/C++ typ).

btUInt základní typ je `unsigned int` (C/C++ typ).

btFloat základní typ je číslo s plovoucí desetinnou čárkou (`FLOAT`).

btBCD základní typ je binární soubor pevně zakódované desetinné číslo (`BCD`).

btBool základní typ je logická hodnota (`BOOL`).

btLong základní typ je `long int` (C/C++ typ).

btULong základní typ je `unsigned long int` (C/C++ typ).

btCurrency základní typ je měna.

btDate základní typ je datum a čas (`DATE`).

btVariant základní typ je typ proměnné struktury (`VARIANT`).

btComplex základní typ je komplexní čísla.

btBit základní typ je tento bit.

btBSTR základní typ je řetězec základní nebo binární (`BSTR`).

btHresult základní typ je `HRESULT`.

## <a name="remarks"></a>Poznámky
Jsou vrácené hodnoty v tento výčet [idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)
- [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)
