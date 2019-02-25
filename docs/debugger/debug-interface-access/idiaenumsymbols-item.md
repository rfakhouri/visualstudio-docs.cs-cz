---
title: Idiaenumsymbols::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Item method
ms.assetid: 2bd1ec04-e677-4e32-8e32-33334f1eed77
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91c230f641612c099495c54db67da9c7e755cbdc
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607132"
---
# <a name="idiaenumsymbolsitem"></a>IDiaEnumSymbols::Item
Načte symbolu pomocí indexu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Item ( 
   DWORD        index,
   IDiaSymbol** symbol
);
```

#### <a name="parameters"></a>Parametry
 index

[in] Index o [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který se má načíst. Index je v rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenumsymbols::get_count –](../../debugger/debug-interface-access/idiaenumsymbols-get-count.md) metody.

  – symbol

[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt představující symbol požadované.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)