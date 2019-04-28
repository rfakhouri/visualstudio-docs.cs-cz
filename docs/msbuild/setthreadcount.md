---
title: SetThreadCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 656e491e683c7ec2de23ea7e49938e833af3a295
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945731"
---
# <a name="setthreadcount"></a>SetThreadCount
Nastaví počet globální vláken a přiřadí tento počet aktuální vlákno.

## <a name="syntax"></a>Syntaxe

```cmd
HRESULT WINAPI SetThreadCount(int threadCount);
```

#### <a name="parameters"></a>Parametry
[in] `threadCount`

 Počet vláken.

## <a name="return-value"></a>Návratová hodnota
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl aktualizován počet vláken.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *FileTracker.h*