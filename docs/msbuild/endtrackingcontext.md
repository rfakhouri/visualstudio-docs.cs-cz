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
ms.openlocfilehash: b7f837e7a983d0f2c2520d7e379ffb49f332c75c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609979"
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
- [StartTrackingContext](../msbuild/starttrackingcontext.md)
