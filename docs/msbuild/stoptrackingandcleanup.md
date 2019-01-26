---
title: StopTrackingAndCleanup | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- StopTrackingAndCleanup
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StopTrackingAndCleanup
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b6ed74dab67cc2ca718ba312fb657659897c78c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54955593"
---
# <a name="stoptrackingandcleanup"></a>StopTrackingAndCleanup
Zastaví všechna sledování a uvolnění paměti používané sledování relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp 
HRESULT WINAPI StopTrackingAndCleanup(void);  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí **HRESULT** s **SUCCEEDED** sadu bitů, pokud se zastavila sledování.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *FileTracker.h*  
  
## <a name="see-also"></a>Viz také:  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)