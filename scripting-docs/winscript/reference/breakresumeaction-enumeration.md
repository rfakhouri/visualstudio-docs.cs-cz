---
title: Breakresumeaction – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: e5c79aacc64eb57282bf09f7e4673980396b37ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955286"
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