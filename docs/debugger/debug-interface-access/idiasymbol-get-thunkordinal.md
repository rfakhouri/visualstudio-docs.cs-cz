---
title: Idiasymbol::get_thunkordinal – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6dadfff62502af59652e9113553e13b4942c540f
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "64822631"
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
Načte převodní rutina typ funkce.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_thunkOrdinal ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí hodnotu z [thunk_ordinal – výčet](../../debugger/debug-interface-access/thunk-ordinal.md) výčet, který určuje typ převodní rutina funkce.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 Tato vlastnost je platná pouze tehdy, pokud symbol jako [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnotu `SymTagThunk`.

 "Převodní rutina" je část kódu, který převede mezi 32-bit paměti adresní prostor (označované také jako plochý adresní prostor) a 16bitových adresní prostor, (označované jako segmentovaným adresní prostor).

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [THUNK_ORDINAL – výčet](../../debugger/debug-interface-access/thunk-ordinal.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)