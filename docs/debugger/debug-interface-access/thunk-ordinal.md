---
title: THUNK_ORDINAL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4c74d7d9f419a524ac7ef4c96d304c366f1a7c14
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
Označí převodu typů.  
  
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
 Standardní převodu.  
  
 THUNK_ORDINAL_ADJUSTOR  
 A `this` likvidátor převodu.  
  
 THUNK_ORDINAL_VCALL  
 Virtuální volání převodu.  
  
 THUNK_ORDINAL_PCODE  
 P-kód převodu.  
  
 THUNK_ORDINAL_LOAD  
 Zpoždění zatížení převodu.  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 Přírůstkové trampoline převodu (trampoline převodu se používá k kolísají volání z jednoho paměťový prostor na jiný).  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 Převodu trampoline bod větve.  
  
## <a name="remarks"></a>Poznámky  
 Volání se vrátí hodnoty v tento výčet [idiasymbol::get_thunkordinal –](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)