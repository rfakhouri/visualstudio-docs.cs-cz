---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: StartTrackingContextWithRoot
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 0d49543bde0195144fb4918e9a9f173f8f9435ea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
Spustí kontextu sledování pomocí souboru odpovědí zadání kořenovou značku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp 
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>Parametry  
 [v]`intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [v]`taskName`  
 Identifikuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.  
  
 [v]`rootMarkerResponseFile`  
 Cesta souboru odpovědí, který obsahuje kořenovou značku. Název kořenového slouží k seskupení všech sledování pro kontext, společně.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)