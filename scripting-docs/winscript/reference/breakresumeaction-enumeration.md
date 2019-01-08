---
title: Breakresumeaction – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- BREAKRESUMEACTION
apilocation:
- scrobj.dll
helpviewer_keywords:
- BREAKRESUMEACTION enumeration
ms.assetid: b39fcc82-7776-4caa-8155-b398de68df03
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3186ac39353d11f327f7940ae5fc03ae2238ddd9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090465"
---
# <a name="breakresumeaction-enumeration"></a>Výčet BREAKRESUMEACTION
Popisuje způsoby, jak pokračovat od bodu přerušení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagBREAKRESUME_ACTION {  
   BREAKRESUMEACTION_ABORT,  
   BREAKRESUMEACTION_CONTINUE,  
   BREAKRESUMEACTION_STEP_INTO,  
   BREAKRESUMEACTION_STEP_OVER,  
   BREAKRESUMEACTION_STEP_OUT,  
   BREAKRESUMEACTION_IGNORE,  
   BREAKRESUMEACTION_STEP_DOCUMENT,  
} BREAKRESUMEACTION;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|BREAKRESUMEACTION_ABORT|Zruší aplikace.|  
|BREAKRESUMEACTION_CONTINUE|Bude nadále spuštěn.|  
|BREAKRESUMEACTION_STEP_INTO|Kroky v postupu.|  
|BREAKRESUMEACTION_STEP_OVER|Kroky v postupu.|  
|BREAKRESUMEACTION_STEP_OUT|Vystoupí z aktuální proceduře.|  
|BREAKRESUMEACTION_IGNORE|Bude nadále spuštěn se stavem.|  
|BREAKRESUMEACTION_STEP_DOCUMENT|Postup následující dokument.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)