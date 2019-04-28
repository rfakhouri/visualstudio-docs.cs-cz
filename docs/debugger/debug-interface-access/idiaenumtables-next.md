---
title: Idiaenumtables::Next – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Next method
ms.assetid: 8d7bd359-d33e-4317-9674-d89283efd7de
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15a9ebbd3a3993568e4b6496e04661a63290399e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832729"
---
# <a name="idiaenumtablesnext"></a>IDiaEnumTables::Next
Načte zadaný počet tabulek v pořadí výčtu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Next ( 
   ULONG       celt,
   IDiaTable** rgelt,
   ULONG*      pceltFetched
);
```

#### <a name="parameters"></a>Parametry
 `celt`

[in] Počet tabulek v enumerátor, který se má načíst.

 `rgelt`

[out] Pole, které je v tankujeme [idiatable –](../../debugger/debug-interface-access/idiatable.md) objekty, které představují požadované tabulky.

 `pceltFetched`

[out] Vrátí počet tabulek v načtených enumerátor.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud nejsou žádné další tabulky. V opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)