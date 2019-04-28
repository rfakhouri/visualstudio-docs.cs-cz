---
title: Idiaenumdebugstreams::get_count – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::get_Count method
ms.assetid: 5c13fa9a-b35e-47b0-806f-1f53bfe1ba89
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5840bbcc012fdcb209fbfb19c0119ad94f3073f2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838438"
---
# <a name="idiaenumdebugstreamsgetcount"></a>IDiaEnumDebugStreams::get_Count
Získá počet datových proudů ladění.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_Count( 
   LONG* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí počet datových proudů ladění k dispozici v tomto výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)
- [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)