---
title: IDiaSymbol::get_isReturnValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 37aaf48a-65cb-4ec2-823e-1c637a9f939c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 25265d25a3f4d89682ff7e4b8d74ee02f3c073c1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54950699"
---
# <a name="idiasymbolgetisreturnvalue"></a>IDiaSymbol::get_isReturnValue
Určuje, zda proměnná nese návratovou hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_isReturnValue(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `BOOL` , která určuje, zda proměnná nese návratovou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)