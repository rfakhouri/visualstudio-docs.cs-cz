---
title: marker_series::write_alert – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic:marker_series::write_alert
helpviewer_keywords:
- Concurrency::diagnostic:marker_series::write_alert method
ms.assetid: 9d5465c7-f862-47a7-b249-4116605075a6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 635f767f97ea3d237aeff843e99735eccae31efc
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613827"
---
# <a name="markerserieswritealert-method"></a>marker_series::write_alert – metoda
Zapíše upozornění do souboru trasování vizualizátoru souběžnosti.

## <a name="syntax"></a>Syntaxe

```cpp
void write_alert(
   _In_ LPCTSTR _Format,
   ...
);
```

#### <a name="parameters"></a>Parametry
 `_Format` Složený řetězec formátu, který obsahuje textu smíšeného s nula nebo více položek formátu, který odpovídá objektům v seznamu argumentů.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *cvmarkersobj.h*

 **Namespace:** Concurrency::diagnostic

## <a name="see-also"></a>Viz také:
- [marker_series – třída](../profiling/marker-series-class.md)