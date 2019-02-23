---
title: StartTrackingContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- StartTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContext
ms.assetid: 720cd295-38e7-4974-86db-b8106b1207ba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c395df1e08f1b4e33e9cd34fec54bdd044f3b4c9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690510"
---
# <a name="starttrackingcontext"></a>StartTrackingContext
Začněte kontext sledování.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WINAPI StartTrackingContext(LPCTSTR intermediateDirectory, LPCTSTR taskName);
```

#### <a name="parameters"></a>Parametry
[in] `intermediateDirectory`

 Adresáře, ve kterém k uložení protokolu sledování.

[in] `taskName`

 Určuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.

## <a name="return-value"></a>Návratová hodnota
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl vytvořen kontext sledování.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *FileTracker.h*