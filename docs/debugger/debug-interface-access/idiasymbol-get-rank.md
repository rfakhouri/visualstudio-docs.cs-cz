---
title: Idiasymbol::get_rank – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_rank method
ms.assetid: 14cc9c4b-a5ec-414a-b01f-4a142c17b7cc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c38962ab5915a4235201e76e1828f84a56af1333
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "64830785"
---
# <a name="idiasymbolgetrank"></a>IDiaSymbol::get_rank
Získá počet rozměrů (počet rozměrů) až po FORTRAN vícerozměrné pole.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_rank ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí počet dimenzí v až po FORTRAN vícerozměrné pole.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 Pořadí odkazuje na počet dimenzí v poli, kde je pole deklarované jako `myarray[1,2,3]`. V tomto příkladu má pořadí 3 až 3 dimenze. Řazení se nevztahuje na C++, který používá koncept pole polí pro každou dimenzi (to znamená `myarray[1][2][3]`).

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)