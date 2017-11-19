---
title: THUNK_ORDINAL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a2711ab101299b47e954e56fcbbae98d9f5fdb6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Idiasymbol::get_thunkordinal –](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)