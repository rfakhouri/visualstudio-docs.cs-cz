---
title: IDiaSymbol::getSrcLineOnTypeDefn | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ad554d18-9988-4b64-ad71-e7594c266e94
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cd81117c11eb42dbccf22e55ee5e294ad9c3c96a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62834361"
---
# <a name="idiasymbolgetsrclineontypedefn"></a>IDiaSymbol::getSrcLineOnTypeDefn
Načte zdrojový soubor a číslo řádku, která označuje, kde je definován zadaný uživatelem definovaného typu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT getSrcLineOnTypeDefn(
   IDiaLineNumber **ppResult);
```

#### <a name="parameters"></a>Parametry
 `ppResult`

[out] A `IDiaLineNumber` objekt, který obsahuje číslo zdrojového souboru a řádku kde definovaný uživatelem.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)