---
title: Idiasymbol::get_haseha – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasEHa method
ms.assetid: cb61dfd9-fe69-461c-8185-288440454864
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 801c98e3eda2ae94ffde75b338cbad7a868f6925
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598164"
---
# <a name="idiasymbolgethaseha"></a>IDiaSymbol::get_hasEHa
Získá příznak, který určuje, zda funkce obsahuje (asynchronní strukturované) zpracování výjimek.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_hasEHa(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parametry
 `pFlag`

[out] Vrátí `TRUE` Pokud funkce má všechny asynchronní zpracování výjimek; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 Je možné kombinovat asynchronní nebo strukturované zpracování výjimek s zpracování výjimek jazyka C++ – vizuální styl, ale vyžaduje přepínače kompilátoru specifické, / EHa ho chcete povolit.

## <a name="requirements"></a>Požadavky

|Požadavek|Popis|
|-----------------|-----------------|
|Záhlaví:|dia2.h|
|Verze:|Ve verzi 8.0 DIA SDK|

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)