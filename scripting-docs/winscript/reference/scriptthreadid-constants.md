---
title: Scriptthreadid – konstanty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- SCRIPTTHREADID
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTTHREADID
ms.assetid: 1df9940c-ad0c-42d8-96b9-6a6abe2382e6
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dfbb39d10d552141a68d40a7be3f1715a80f8f57
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840198"
---
# <a name="scriptthreadid-constants"></a>SCRIPTTHREADID – konstanty
Slouží k určení typu vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef DWORD SCRIPTTHREADID;  
```  
  
## <a name="constants"></a>Konstanty  
  
|Konstanta|Hodnota|Význam|  
|--------------|-----------|-------------|  
|SCRIPTTHREADID_CURRENT|0xFFFFFFFD|Aktuálně spuštěné vlákno.|  
|SCRIPTTHREADID_BASE|0xFFFFFFFE|Základní podprocesu. To znamená, že byla vytvořena instance vláken, ve kterém skriptovací stroje.|  
|SCRIPTTHREADID_ALL|0xFFFFFFFF|Všechna vlákna.|  
  
## <a name="remarks"></a>Poznámky  
 `SCRIPTTHREADID` Typ se používá v `IActiveScript::GetCurrentScriptThreadID`, `IActiveScript::GetScriptThreadID`, `IActiveScript::GetScriptThreadState`, a `IActiveScript::InterruptScriptThread`, ale konstanty jde použít jenom ve `IActiveScript::GetScriptThreadState` a `IActiveScript::InterruptScriptThread`.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)   
 [IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)   
 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)