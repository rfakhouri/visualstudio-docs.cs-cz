---
title: Scriptthreadstate – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- SCRIPTTHREADSTATE
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTTHREADSTATE enum
ms.assetid: 975ec66b-c095-40ac-8ba9-631adb97b589
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 906a309b25a1fe606fb37f8cbab70040e5a4c46f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840184"
---
# <a name="scriptthreadstate-enumeration"></a>SCRIPTTHREADSTATE – výčet
Určuje stav vlákna v skriptovací stroj. Tento výčet je používán [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagSCRIPTTHREADSTATE {  
    SCRIPTTHREADSTATE_NOTINSCRIPT  = 0,  
    SCRIPTTHREADSTATE_RUNNING      = 1  
} SCRIPTTHREADSTATE;  
```  
  
## <a name="enumeration-values"></a>Hodnoty výčtu  
  
|||  
|-|-|  
|SCRIPTTHREADSTATE_NOTINSCRIPT|Zadané vlákno není aktuálně skriptované událostí, zpracování okamžitě provést text skriptu, nebo spuštění skriptu makra.|  
|SCRIPTTHREADSTATE_RUNNING|Zadané vlákno je aktivně skriptované událostí, zpracování okamžitě provést text skriptu, nebo spuštění skriptu makra.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a kódy chyb aktivních skriptů](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)