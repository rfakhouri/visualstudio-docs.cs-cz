---
title: Idiasymbol::get_slot – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_slot method
ms.assetid: 97e405b8-483f-4da0-91e7-ca4d88251ecd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a8f56068e1278fcf1bbe6b1feb9354f229f7d09
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53988998"
---
# <a name="idiasymbolgetslot"></a>IDiaSymbol::get_slot
Číslo pozice v umístění načte. Použít, když [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) je `LocIsSlot`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_slot (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí číslo pozice v umístění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)