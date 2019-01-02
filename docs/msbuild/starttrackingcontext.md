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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a12945400c1d479ad8543b2c8f050098d326881
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844116"
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