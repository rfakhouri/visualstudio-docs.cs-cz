---
title: StartTrackingContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- StartTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContext
ms.assetid: 720cd295-38e7-4974-86db-b8106b1207ba
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0aba760e72cb2edf0d35927d76665be610626897
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="starttrackingcontext"></a>StartTrackingContext
Spusťte sledování kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT WINAPI StartTrackingContext(LPCTSTR intermediateDirectory, LPCTSTR taskName);  
```  
  
#### <a name="parameters"></a>Parametry  
 [in] `intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [in] `taskName`  
 Identifikuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Header:** FileTracker.h