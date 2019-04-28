---
title: Idiasession::get_loadaddress – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::get_loadAddress method
ms.assetid: 5162ae1a-38e3-4571-8995-4ed9be1dec3e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fed7653b5f1a270d2e297cdd2b59366b5b563c3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839183"
---
# <a name="idiasessiongetloadaddress"></a>IDiaSession::get_loadAddress
Načte adresu zatížení pro spustitelný soubor, který odpovídá symboly v tomto úložišti symbolů.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_loadAddress ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí virtuální adresy (VA), kde je načtena souboru .exe nebo .dll soubor.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Adresa vrácené zatížení je vždy nula není-li nastavit pomocí [idiasession::put_loadaddress –](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) metoda.

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSession::put_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)