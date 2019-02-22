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
ms.openlocfilehash: 14ae065f16c2d047311308d63da7680a61fa22ad
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622215"
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
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)