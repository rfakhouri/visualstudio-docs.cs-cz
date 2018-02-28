---
title: IDiaSymbol::get_restrictedType | Microsoft Docs
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
ms.assetid: c48b00a6-26b0-47b0-b824-fe44dedbc756
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 405dbeb5354a1f7d04ab22ef87f5b026c08867e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetrestrictedtype"></a>IDiaSymbol::get_restrictedType
Určuje, zda `this` ukazatel je označený jako s omezeným přístupem.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_restrictedType(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel na `BOOL` který určuje, zda `this` ukazatel je označený jako s omezeným přístupem.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)