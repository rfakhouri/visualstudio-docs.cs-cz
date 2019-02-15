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
ms.openlocfilehash: 482c5f7bd0565c3b6ece124c88bd5e225b4cc7dd
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318521"
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
THUNK_ORDINAL_NOTYPE  
Standardní převodní rutina.

THUNK_ORDINAL_ADJUSTOR  
A `this` likvidátor převodní rutina.

THUNK_ORDINAL_VCALL  
Virtuální volání převodní rutina.

THUNK_ORDINAL_PCODE  
Převodní rutina P-code.

THUNK_ORDINAL_LOAD  
Převodní rutina zatížení zpoždění.

THUNK_ORDINAL_TRAMP_INCREMENTAL  
Převodní rutina přírůstkové trampoline (trampoline převodní rutina se používá k odraz volání z jednoho paměťového prostoru do jiného).

THUNK_ORDINAL_TRAMP_BRANCHISLAND  
Převodní rutina trampoline bod větve.

## <a name="remarks"></a>Poznámky
Během volání se vrátí hodnoty v tento výčet [idiasymbol::get_thunkordinal –](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
[Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)
