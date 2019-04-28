---
title: THUNK_ORDINAL – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 776ee35e57b62463d47fc6f7fa26133f507f16f9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62854433"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
Určuje typy převodní rutina.

## <a name="syntax"></a>Syntaxe

```C++
typedef enum THUNK_ORDINAL {
    THUNK_ORDINAL_NOTYPE,
    THUNK_ORDINAL_ADJUSTOR,
    THUNK_ORDINAL_VCALL,
    THUNK_ORDINAL_PCODE,
    THUNK_ORDINAL_LOAD

    // trampoline thunk ordinals - only for use in Trampoline thunk symbols
    THUNK_ORDINAL_TRAMP_INCREMENTAL,
    THUNK_ORDINAL_TRAMP_BRANCHISLAND,
} THUNK_ORDINAL;
```

## <a name="elements"></a>Elementy
Standardní THUNK_ORDINAL_NOTYPE převodní rutina.

THUNK_ORDINAL_ADJUSTOR A `this` likvidátor převodní rutina.

Převodní rutina THUNK_ORDINAL_VCALL virtuální volání.

Převodní rutina THUNK_ORDINAL_PCODE P-code.

Převodní rutina zatížení THUNK_ORDINAL_LOAD zpoždění.

Přírůstkové THUNK_ORDINAL_TRAMP_INCREMENTAL trampoline převodní rutina (trampoline převodní rutina se používá k odraz volání z jednoho paměťového prostoru do jiného).

Převodní rutina trampoline bodu THUNK_ORDINAL_TRAMP_BRANCHISLAND větve.

## <a name="remarks"></a>Poznámky
Během volání se vrátí hodnoty v tento výčet [idiasymbol::get_thunkordinal –](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)
