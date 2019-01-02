---
title: Idiasymbol::get_typeids – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d038c0be6f023206c6a96ec59389ec4063d975fd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53880085"
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
Načte pole hodnot typu specifických pro kompilátor identifikátor pro tento symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cTypeIds`  
 [in] Velikost vyrovnávací paměti pro data.  
  
 `pcTypeIds`  
 [out] Vrátí počet `typeIds` zapsána, nebo pokud `typeIds` je `NULL`, pak celkový počet identifikátorů typu k dispozici.  
  
 `typeIds[]`  
 [out] Pole, které se vyplní identifikátory typu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)