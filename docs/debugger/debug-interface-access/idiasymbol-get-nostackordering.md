---
title: Idiasymbol::get_nostackordering – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_noStackOrdering method
ms.assetid: a1753917-705b-4165-9880-d05e91e6dcb4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d36a934fe9475613e916d51290ac6f8960a6b42
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399289"
---
# <a name="idiasymbolgetnostackordering"></a>IDiaSymbol::get_noStackOrdering
Tato funkce použije příznak, který označuje, zda může být jako součást kontrolou vyrovnávací paměti zásobníku provést žádné řazení zásobníku ([/GS (Kontrola zabezpečení vyrovnávací paměti)](/cpp/build/reference/gs-buffer-security-check) – možnost kompilátoru).

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_noStackOrdering(
   BOOL *pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí `TRUE` Pokud žádné řazení zásobníku nedala provést jako součást kontrolou zásobníku vyrovnávací paměti; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="requirements"></a>Požadavky

|Požadavek|Popis|
|-----------------|-----------------|
|Záhlaví:|dia2.h|
|Verze:|Ve verzi 8.0 DIA SDK|

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [/GS (kontrola zabezpečení vyrovnávací paměti)](/cpp/build/reference/gs-buffer-security-check)