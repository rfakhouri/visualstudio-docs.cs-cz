---
title: StartTrackingContextWithRoot | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- StartTrackingContextWithRoot
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 53f2c1ebd5896eaa8a4b9d5ff4e5cb7856a1f8e2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690485"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
Spouští kontext sledování pomocí souboru odpovědí. určení kořenové značky.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);
```

#### <a name="parameters"></a>Parametry
[in] `intermediateDirectory`

 Adresáře, ve kterém k uložení protokolu sledování.

[in] `taskName`

 Určuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.

[in] `rootMarkerResponseFile`

 Cesta souboru odpovědí obsahující kořenové značky. Název kořenového slouží k seskupení všech sledování pro kontext, společně.

## <a name="return-value"></a>Návratová hodnota
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl vytvořen kontext sledování.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *FileTracker.h*

## <a name="see-also"></a>Viz také:
- [StartTrackingContext](../msbuild/starttrackingcontext.md)