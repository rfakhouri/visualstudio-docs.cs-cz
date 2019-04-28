---
title: marker_series::marker_series – konstruktor | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series constructor
ms.assetid: 042c7d23-f1d8-4e09-9e76-a21c30243790
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5178b2cebdfa4246256aef6334e026ef091fa553
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62831410"
---
# <a name="markerseriesmarkerseries-constructor"></a>marker_series::marker_series – konstruktor
Inicializuje novou instanci třídy `marker_series` třídy.

## <a name="syntax"></a>Syntaxe

```cpp
marker_series();
marker_series(
   _In_ LPCTSTR _SeriesName
);
marker_series(
   _In_ const GUID* _ProviderGuid
);
marker_series(
   _In_ const GUID* _ProviderGuid,
   _In_ LPCTSTR _SeriesName
);
```

#### <a name="parameters"></a>Parametry
 `_SeriesName` Název řady k vytvoření.

 `_ProviderGuid` Identifikátor GUID zprostředkovatele řady.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *cvmarkersobj.h*

 **Namespace:** Concurrency::diagnostic

## <a name="see-also"></a>Viz také:
- [marker_series – třída](../profiling/marker-series-class.md)