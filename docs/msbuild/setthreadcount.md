---
title: SetThreadCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: SetThreadCount
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53b4d68cfd664e5b9b3385bbbbc9228fe57e566d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="setthreadcount"></a>SetThreadCount
Nastaví počet globální vláken a přiřadí tento počet aktuální vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>Parametry  
 [v]`threadCount`  
 Počet vláken používaných.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud byl aktualizován počet vláken.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h