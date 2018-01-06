---
title: "Idiasymbol::get_thunkordinal – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2ef3c35c1732c4177edfa6d3bc41faacc1371aa5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
Načte typ převodu funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_thunkOrdinal (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu z [THUNK_ORDINAL – výčet](../../debugger/debug-interface-access/thunk-ordinal.md) výčet, který určuje typ převodu funkce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je platná pouze tehdy, pokud symbol jako [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnotu `SymTagThunk`.  
  
 "Převodu" je úsek kódu, který převádí mezi adresní prostor 32-bit paměti (také označované jako plochý adresní prostor) a 16bitové adresní prostor (označované jako segmentovaný adresní prostor).  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [THUNK_ORDINAL – výčet](../../debugger/debug-interface-access/thunk-ordinal.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)