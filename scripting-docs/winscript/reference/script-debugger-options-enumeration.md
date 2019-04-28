---
title: Výčet SCRIPT_DEBUGGER_OPTIONS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 404d3939e0a328beb5e2413d25885fddf8478ead
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443645"
---
# <a name="scriptdebuggeroptions-enumeration"></a>Výčet SCRIPT_DEBUGGER_OPTIONS
Označuje sadu možností a/nebo funkce, které se vztahují na připojený ladicí program. Použít v [IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md) a [IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
> Tyto konstanty jsou implementovány pomocí PDM v10.0 a větší. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef SCRIPT_DEBUGGER_OPTIONS  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Value|Popis|  
|------------|-----------|-----------------|  
|SDO_NONE|0x00000000|Nejsou nastaveny žádné možnosti.|  
|SDO_ENABLE_FIRST_CHANCE_EXCEPTIONS|0x00000001|Označuje, že spuštění skriptu by měla vyvolat události BREAKREASON_ERROR, kdy je vyvolána výjimka. Tato možnost může nastavit ladicím programem nebo nastavit kódem uživatele prostřednictvím `Debug.enableFirstChanceExceptions(<true&#124;false>)`.|  
|SDO_ENABLE_WEB_WORKER_SUPPORT|0x00000002|Označuje, že na připojený ladicí program podporuje webových pracovních procesů.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)