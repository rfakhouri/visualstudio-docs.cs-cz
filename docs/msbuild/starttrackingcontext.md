---
title: StartTrackingContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- StartTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContext
ms.assetid: 720cd295-38e7-4974-86db-b8106b1207ba
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 52c564ea06adbb7e7edd957bf4fb23e30cdf2510
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="starttrackingcontext"></a>StartTrackingContext
Spusťte sledování kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT WINAPI StartTrackingContext(LPCTSTR intermediateDirectory, LPCTSTR taskName);  
```  
  
#### <a name="parameters"></a>Parametry  
 [v] `intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [v] `taskName`  
 Identifikuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h