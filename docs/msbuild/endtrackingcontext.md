---
title: EndTrackingContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- EndTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- EndTrackingContext
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f380b57b95cfc0601984794bf02ad4ed145bac5
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55853336"
---
# <a name="endtrackingcontext"></a>EndTrackingContext
Ukončit aktuální kontext sledování.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WINAPI EndTrackingContext();
```

## <a name="return-value"></a>Návratová hodnota
**HRESULT** s **SUCCEEDED** sadu bitů, pokud kontext sledování bylo ukončeno.

## <a name="requirements"></a>Požadavky
**Záhlaví:** *FileTracker.h*

## <a name="see-also"></a>Viz také:
[StartTrackingContext](../msbuild/starttrackingcontext.md)
