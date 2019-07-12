---
title: IDiaSymbol::get_registerId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3e2b1cbb6837ca139e735bef17bc0c2712d9cae7
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "64786584"
---
# <a name="idiasymbolgetregisterid"></a>IDiaSymbol::get_registerId
Načte register označení umístění při [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) je nastavena na `LocIsEnregistered`.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_registerId ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí hodnotu registru označení umístění.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 Pokud symbol je relativní vzhledem k registru, to znamená, pokud symbolu [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) je nastavena na `LocIsRegRel`, použijte `get_registerId` metoda za nímž následuje volání [idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md) metodu k získání posun z registru, kde se nachází symbolu.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)