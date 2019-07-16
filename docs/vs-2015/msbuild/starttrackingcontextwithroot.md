---
title: StartTrackingContextWithRoot | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- StartTrackingContextWithRoot
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 68e80da01a0ab1ad59bbb5bdb06c92c1a11a8ac1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182325"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spouští kontext sledování pomocí souboru odpovědí. určení kořenové značky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 [HRESULT] ()<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) s ([úspěch]<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) sadu bitů, pokud byl vytvořen kontext sledování.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)
