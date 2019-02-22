---
title: IDiaSymbol::get_isAcceleratorPointerTagLiveRange | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d195aec4-6d3c-42e0-88a5-3d463539f0b8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8bf20f43fcc8da48a6e1ec1dfd0f65b14f8ad86
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640243"
---
# <a name="idiasymbolgetisacceleratorpointertagliverange"></a>IDiaSymbol::get_isAcceleratorPointerTagLiveRange
Získá příznak označující, zda symbol odpovídá *definice rozsahu symbol* pro komponentu značky v kódu zkompilovaném pro akcelerátor AMP C++ proměnné ukazatele. Definice rozsahu symbol je umístění proměnnou rozsahu adres.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_isAcceleratorPointerTagLiveRange(
   BOOL* pFlag);
```

#### <a name="parameters"></a>Parametry
 `pFlag`

[out] Ukazatel `BOOL` , která označuje, zda symbol odpovídá symbolu definice rozsahu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)