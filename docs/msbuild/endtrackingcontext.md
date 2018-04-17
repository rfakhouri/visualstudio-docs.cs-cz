---
title: EndTrackingContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- EndTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- EndTrackingContext
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c64ad01018494d66ba181af371ae8cd15fb6f4d7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="endtrackingcontext"></a>EndTrackingContext
Ukončete aktuální kontext sledování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI EndTrackingContext();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování bylo ukončeno.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)