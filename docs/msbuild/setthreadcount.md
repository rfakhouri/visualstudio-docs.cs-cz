---
title: SetThreadCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c45b32ad965bd3b01becf5cb99b1e1366607d13d
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="setthreadcount"></a>SetThreadCount
Nastaví počet globální vláken a přiřadí tento počet aktuální vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>Parametry  
 [in] `threadCount`  
 Počet vláken používaných.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud byl aktualizován počet vláken.  
  
## <a name="requirements"></a>Požadavky  
 **Header:** FileTracker.h