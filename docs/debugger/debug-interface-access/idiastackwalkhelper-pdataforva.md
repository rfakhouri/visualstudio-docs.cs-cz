---
title: IDiaStackWalkHelper::pdataForVA | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6315032a36369eff7a5d43241ae4968a64ad42cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62831892"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
Vrátí přidružený virtuální adresu PDATA datového bloku.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT pdataForVA( 
   ULONGLONG  va,
   DWORD      cbData,
   DWORD*     pcbData,
   BYTE*      pbData
);
```

#### <a name="parameters"></a>Parametry
 `va`

[in] Určuje virtuální adresu dat, která poskytuje.

 `cbData`

[in] Velikost dat v bajtech získat.

 `pcbData`

[out] Vrátí skutečný objem dat v bajtech, ke které byl získán.

 `pbData`

[out v] Vyrovnávací paměť je vyplní požadovaná data. Nemůže být `NULL`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistuje žádný PDATA pro zadanou adresu. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 PDATA (oddíl s názvem ".pdata") kompilace obsahuje informace o zpracování výjimek pro funkce.

 Volající ví, kolik dat má být vrácen tak má volající není potřeba zeptejte, kolik dat je k dispozici. Proto je přijatelné pro implementace této metody vrátit chybu, pokud `pbData` parametr `NULL`.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)