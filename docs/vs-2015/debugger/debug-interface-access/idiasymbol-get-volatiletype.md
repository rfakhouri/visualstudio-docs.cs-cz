---
title: Idiasymbol::get_volatiletype – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_volatileType method
ms.assetid: 19782a4d-40a8-467b-ab7d-58bc4d812309
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d36d688c29894bd65eae29e033ef1d94869e04fd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386582"
---
# <a name="idiasymbolgetvolatiletype"></a>IDiaSymbol::get_volatileType
Získá příznak, který určuje, zda je uživatelský datový typ (UDT) typu volatile.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_volatileType ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí `TRUE` Pokud UDT volatile; jinak vrátí hodnotu, vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 V jazyce C++, může být označena UDT `volatile` – klíčové slovo, která udává, že jeho obsah nelze považovat za existovat jeden přístup na další.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)