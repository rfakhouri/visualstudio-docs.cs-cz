---
title: IDiaSymbol::get_isAcceleratorStubFunction | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cc4ea375-76f6-4ba8-baed-c5fa82108137
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bbcfbfcd1e95a45388d0b7c0626f1cd529607ce4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613502"
---
# <a name="idiasymbolgetisacceleratorstubfunction"></a>IDiaSymbol::get_isAcceleratorStubFunction
Určuje, zda symbol odpovídá symbol funkce nejvyšší úrovně pro shader kompilován pro akcelerátor, který odpovídá `parallel_for_each` volání.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_isAcceleratorStubFunction(
   BOOL* pFlag);
```

#### <a name="parameters"></a>Parametry
 `pFlag`

[out] Ukazatel `BOOL` , která označuje, zda symbol odpovídá symbol funkce nejvyšší úrovně pro shader kompilován pro akcelerátor, který odpovídá `parallel_for_each` volání.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)