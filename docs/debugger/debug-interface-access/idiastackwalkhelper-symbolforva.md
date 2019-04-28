---
title: Idiastackwalkhelper::symbolforva – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01c457947eb84859f2ce92378688dd03c624c86d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837885"
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
Načte symbol, který obsahuje zadanou virtuální adresu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT symbolForVA( 
   ULONGLONG     va,
   IDiaSymbol**  ppSymbol
);
```

#### <a name="parameters"></a>Parametry
 `va`

[in] Virtuální adresu, která je součástí požadované symbol. Musí být symbol `SymTagFunctionType` (hodnoty z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčet).

 `ppSymbol`

[out] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt představující symbol na zadané adrese.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)