---
title: Idiasymbol::get_noreturn – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_noReturn method
ms.assetid: 704c1cc0-5b84-4334-a02a-70f43aff39d5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0857939289091d22aaafb5dc5bb009d4af0e00bb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399336"
---
# <a name="idiasymbolgetnoreturn"></a>IDiaSymbol::get_noReturn
Získá příznak, který určuje, zda funkce byla označena jako nikdy vrátilo [noreturn](/cpp/cpp/noreturn) atribut.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_noReturn(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parametry
 pFlag

[out] Vrátí `TRUE` Pokud funkce byla deklarována jako nikdy vrátilo `noreturn` atribut; v opačném případě vrátí `FALSE`.

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
- [noreturn](/cpp/cpp/noreturn)