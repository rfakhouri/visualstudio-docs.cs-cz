---
title: IDiaSymbol::get_numberOfRegisterIndices | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1ec8b8ea-e423-4327-8dc0-a390e6e3ffb0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 699cabda0fc6cbdfdf61ec14b5919ffffd62819e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867975"
---
# <a name="idiasymbolgetnumberofregisterindices"></a>IDiaSymbol::get_numberOfRegisterIndices
Získá počet indexů registru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_numberOfRegisterIndices(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `DWORD` , který obsahuje počet indexů registru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)