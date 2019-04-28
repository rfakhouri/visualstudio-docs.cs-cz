---
title: Idiaenumsegments::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Item method
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 87751dcca1e2109db53c9d6dd4594bc969ffc684
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833269"
---
# <a name="idiaenumsegmentsitem"></a>IDiaEnumSegments::Item
Segment, který načte prostřednictvím indexu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Item ( 
   DWORD         index,
   IDiaSegment** segment
);
```

#### <a name="parameters"></a>Parametry
 index

[in] Index o [idiasegment –](../../debugger/debug-interface-access/idiasegment.md) objekt, který se má načíst. Index je v rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenumsegments::get_count –](../../debugger/debug-interface-access/idiaenumsegments-get-count.md) metody.

 segment

[out] Vrátí [idiasegment –](../../debugger/debug-interface-access/idiasegment.md) objekt představující požadovaný segment.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)