---
title: "Idiasymbol::get_optimizedcodedebuginfo – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_optimizedCodeDebugInfo method
ms.assetid: 57ef4170-37a9-46b0-8217-c1a674725113
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c0ae8a0ef1e088667f51fa2f5886601cc8ddfd25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetoptimizedcodedebuginfo"></a>IDiaSymbol::get_optimizedCodeDebugInfo
Načte příznak, který určuje, jestli funkce obsahuje informace o ladění, která je specifická pro optimalizovaný kód.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_optimizedCodeDebugInfo(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Vrátí `TRUE` Pokud optimalizované funkce nebo popisek obsahuje informace o ladění; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)