---
title: Cvreleasemarkerseries – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d100b7ff37ea5a3cd224fd420f14e4cb23061903
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974139"
---
# <a name="cvreleasemarkerseries-function"></a>Cvreleasemarkerseries – funkce
Uvolní značky řady. Nepoužívejte objekt řady značky po uvolnění jinak aplikace, mohou selhat. Nepodařilo se uvolnit značky řady způsobí, že nevracení paměti.

## <a name="syntax"></a>Syntaxe

```C
HRESULT CvReleaseMarkerSeries(
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries
);
```

#### <a name="parameters"></a>Parametry
 `pMarkerSeries` Adresa proměnné objektu zprostředkovatele. Adresa nesmí být NULL, proměnná může mít libovolnou hodnotu.

## <a name="return-value"></a>Návratová hodnota
 S_OK při řady značky se úspěšně uvolnily nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.

## <a name="requirements"></a>Požadavky
 **Header:** *cvmarkers.h*

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)