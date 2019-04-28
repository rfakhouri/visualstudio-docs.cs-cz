---
title: marker_importance – výčet | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords:
- Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b3f5cfb583ec4fceb9fb7428b08c00f6ca8e26b6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62999964"
---
# <a name="markerimportance-enumeration"></a>marker_importance – výčet
Představuje úroveň důležitosti značek Vizualizátor souběžnosti.

## <a name="syntax"></a>Syntaxe

```cpp
enum marker_importance;
```

## <a name="members"></a>Členové

### <a name="values"></a>Hodnoty

|Název|Popis|
|----------|-----------------|
|`critical_importance`|Určuje, že má značku stěžejní význam.|
|`high_importance`|Určuje, že značky má vysokou důležitostí.|
|`low_importance`|Určuje, zda má značku s nízkou důležitostí.|
|`normal_importance`|Určuje, že značky má normální význam.|

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *cvmarkersobj.h*

 **Namespace:** Concurrency::diagnostic

## <a name="see-also"></a>Viz také:
- [Diagnostic – obor názvů](../profiling/diagnostic-namespace.md)