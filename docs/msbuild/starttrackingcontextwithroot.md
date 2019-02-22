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
ms.openlocfilehash: 63c287339685e6d5f7e1b28c697de2084aba7b22
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618962"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
Spouští kontext sledování pomocí souboru odpovědí. určení kořenové značky.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);
```

#### <a name="parameters"></a>Parametry
- [in] `intermediateDirectory` Adresáře, ve kterém k uložení protokolu sledování.

- [in] `taskName` Identifikuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.

- [in] `rootMarkerResponseFile` Cesty obsahující značku kořenového souboru odpovědí. Název kořenového slouží k seskupení všech sledování pro kontext, společně.

## <a name="return-value"></a>Návratová hodnota
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl vytvořen kontext sledování.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *FileTracker.h*

## <a name="see-also"></a>Viz také:
- [StartTrackingContext](../msbuild/starttrackingcontext.md)