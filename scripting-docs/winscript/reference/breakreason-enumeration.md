---
title: Breakreason – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- BREAKREASON
apilocation:
- scrobj.dll
helpviewer_keywords:
- BREAKREASON enumeration
ms.assetid: bde07ede-2f9b-4fa2-affc-f9405683f5f7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 939d9f36c9838f02e58bc433d1a7bb9bef43c28d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160586"
---
# <a name="breakreason-enumeration"></a>Výčet BREAKREASON
Označuje, co způsobilo přerušení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagBREAKREASON {  
   BREAKREASON_STEP,  
   BREAKREASON_BREAKPOINT,  
   BREAKREASON_DEBUGGER_BLOCK,  
   BREAKREASON_HOST_INITIATED,  
   BREAKREASON_LANGUAGE_INITIATED,  
   BREAKREASON_DEBUGGER_HALT,  
   BREAKREASON_ERROR,  
   BREAKREASON_JIT  
} BREAKREASON;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|BREAKREASON_STEP|Modul jazyka je v režimu krokování.|  
|BREAKREASON_BREAKPOINT|Modul jazyka došlo k explicitní zarážku.|  
|BREAKREASON_DEBUGGER_BLOCK|Modul jazyka došlo k bloku ladicí program v jiném vlákně.|  
|BREAKREASON_HOST_INITIATED|Hostitel požadovaná přerušení.|  
|BREAKREASON_LANGUAGE_INITIATED|Modul jazyk požadovaný přerušení.|  
|BREAKREASON_DEBUGGER_HALT|Ladicí program integrované vývojové prostředí si vyžádal přerušení.|  
|BREAKREASON_ERROR|Chyba spuštění způsobila přerušení.|  
|BREAKREASON_JIT|Způsobené při spuštění ladění JIT.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)