---
title: IDiaSymbol::get_isOptimizedAway | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c18b1e38-b152-4a13-aba0-59faded5b2e6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0f8910d35106574912e4a01f7995bfe0f503e3f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836235"
---
# <a name="idiasymbolgetisoptimizedaway"></a>IDiaSymbol::get_isOptimizedAway
Určuje, zda je proměnná je vypuštěn.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_isOptimizedAway(
   BOOL* pRetVal);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Ukazatel `BOOL` , která určuje, zda je proměnná je vypuštěn.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)