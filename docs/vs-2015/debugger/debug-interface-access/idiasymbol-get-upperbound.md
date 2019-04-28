---
title: Idiasymbol::get_upperbound – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_upperBound method
ms.assetid: a77dcafa-ea3f-45da-826d-8f9b4489a03f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f965cddfa9d5d071bd08e4473cff49c82703d7ec
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386913"
---
# <a name="idiasymbolgetupperbound"></a>IDiaSymbol::get_upperBound
Načte symbol představující horní mez až po FORTRAN dimenze pole.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_upperBound ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který představuje horní mez až po FORTRAN dimenze pole.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)