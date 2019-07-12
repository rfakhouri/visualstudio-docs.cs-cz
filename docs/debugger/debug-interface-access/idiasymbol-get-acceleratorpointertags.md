---
title: IDiaSymbol::get_acceleratorPointerTags | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c1724ee3e81ac00ed048f323105842361ec22bc7
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "62827291"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
Vrátí všechny akcelerátoru hodnoty značky ukazatele, které odpovídají funkci jazyka C++ AMP akcelerátor zástupné procedury.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_acceleratorPointerTags(
   DWORD          cnt,
   DWORD*         pcnt,
   DWORD*         pPointerTags);
```

#### <a name="parameters"></a>Parametry
 `cnt`

[in] Velikost pole výstup `pPointerTags`.

 `pcnt`

[out] Počet značek ukazatel akcelerátoru v C++ AMP akcelerátor zástupné procedury funkcí.

 `pPointerTags`

[out] A `DWORD` pole ukazatel, který je vyplněna hodnot značek akcelerátoru ukazatel v C++ AMP akcelerátor zástupné procedury funkcí.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je volána na `IDiaSymbol` rozhraní, který odpovídá zástupné procedury funkce C++ AMP akcelerátor.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)