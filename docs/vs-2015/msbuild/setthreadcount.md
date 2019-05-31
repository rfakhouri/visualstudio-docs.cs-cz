---
title: SetThreadCount | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- SetThreadCount
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 79987c77da7959c4ba37a4ae8e5b689a052cbbbc
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59666673"
---
# <a name="setthreadcount"></a>SetThreadCount
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nastaví počet globální vláken a přiřadí tento počet aktuální vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>Parametry  
 [in] `threadCount`  
 Počet vláken.  
  
## <a name="return-value"></a>Návratová hodnota  
 [HRESULT] ()<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) s ([úspěch]<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) sadu bitů, pokud byl aktualizován počet vláken.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h
