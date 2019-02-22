---
title: Idiasymbol::get_sealed – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_sealed method
ms.assetid: cd1fef1f-47de-47c7-885f-f6f0a9a07d8c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e581e510ca553dda98689c3e8c5b38dc567f2a06
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628027"
---
# <a name="idiasymbolgetsealed"></a>IDiaSymbol::get_sealed
Získá příznak, který určuje, zda je třída nebo metoda je zapečetěná.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_sealed( 
   BOOL* pRetVal)
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí `TRUE` Pokud třída nebo metoda je zapečetěná; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 Zapečetěnou třídu nelze použít jako základní třídu. Zapečetěné metody nemůže být overidden.

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2.h

 Knihovna: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)