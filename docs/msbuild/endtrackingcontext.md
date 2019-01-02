---
title: EndTrackingContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- EndTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- EndTrackingContext
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fba2d86ca02bf0ddc12e288b3bcbbd4b7189120e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53911504"
---
# <a name="endtrackingcontext"></a>EndTrackingContext
Ukončit aktuální kontext sledování.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WINAPI EndTrackingContext();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud kontext sledování bylo ukončeno.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *FileTracker.h*  
  
## <a name="see-also"></a>Viz také:  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)