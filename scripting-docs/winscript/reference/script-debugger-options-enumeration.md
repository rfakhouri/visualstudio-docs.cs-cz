---
title: Výčet SCRIPT_DEBUGGER_OPTIONS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SCRIPT_DEBUGGER_OPTIONS Enumeration
ms.assetid: aef41ec0-6f65-48e8-a69e-44b4e4fb929f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e35d90a3750c759282d86c7383bf25204fbf4fcd
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088592"
---
# <a name="scriptdebuggeroptions-enumeration"></a>Výčet SCRIPT_DEBUGGER_OPTIONS
Označuje sadu možností a/nebo funkce, které se vztahují na připojený ladicí program. Použít v [IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md) a [IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
>  Tyto konstanty jsou implementovány pomocí PDM v10.0 a větší. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef SCRIPT_DEBUGGER_OPTIONS  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Hodnota|Popis|  
|------------|-----------|-----------------|  
|SDO_NONE|0x00000000|Nejsou nastaveny žádné možnosti.|  
|SDO_ENABLE_FIRST_CHANCE_EXCEPTIONS|0x00000001|Označuje, že spuštění skriptu by měla vyvolat události BREAKREASON_ERROR, kdy je vyvolána výjimka. Tato možnost může nastavit ladicím programem nebo nastavit kódem uživatele prostřednictvím `Debug.enableFirstChanceExceptions(<true&#124;false>)`.|  
|SDO_ENABLE_WEB_WORKER_SUPPORT|0x00000002|Označuje, že na připojený ladicí program podporuje webových pracovních procesů.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)