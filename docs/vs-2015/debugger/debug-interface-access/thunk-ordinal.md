---
title: THUNK_ORDINAL – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cf4a6f96eda9a44e10975ffc1a8262030180b302
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632228"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [thunk_ordinal –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/thunk-ordinal).  
  
Určuje typy převodní rutina.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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



