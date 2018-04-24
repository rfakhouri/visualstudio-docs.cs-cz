---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da93697f273257d166bf377e9c84b03d59d06f78
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
Spustí kontextu sledování pomocí souboru odpovědí zadání kořenovou značku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp 
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>Parametry  
 [v] `intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [v] `taskName`  
 Identifikuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.  
  
 [v] `rootMarkerResponseFile`  
 Cesta souboru odpovědí, který obsahuje kořenovou značku. Název kořenového slouží k seskupení všech sledování pro kontext, společně.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)