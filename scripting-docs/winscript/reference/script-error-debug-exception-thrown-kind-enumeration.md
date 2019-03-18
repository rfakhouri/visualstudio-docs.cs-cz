---
title: Výčet SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b3aa4966-e110-4b30-b368-1281a9740dbd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9dae0161e3337411a56e316e04cf467a1f05e6a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58155716"
---
# <a name="scripterrordebugexceptionthrownkind-enumeration"></a>Výčet SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND
Označuje druh vyvolané výjimky. Tento výčet je používán [IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md) metody.  
  
> [!IMPORTANT]
>  Tyto konstanty jsou implementovány modulem PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Hodnota|Popis|  
|------------|-----------|-----------------|  
|ETK_FIRST_CHANCE|0x00000000|Tato výjimka je výjimka první příležitosti.|  
|ETK_USER_UNHANDLED|0x00000001|Tato výjimka není ošetřena v uživatelském kódu.|  
|ETK_UNHANDLED|0x00000002|Tato výjimka není ošetřena v kódu.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptErrorDebug110 – rozhraní](../../winscript/reference/iactivescripterrordebug110-interface.md)