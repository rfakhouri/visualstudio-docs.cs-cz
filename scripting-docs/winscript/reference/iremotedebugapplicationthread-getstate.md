---
title: IRemoteDebugApplicationThread::GetState | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.GetState
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::GetState
ms.assetid: 44503a78-efa9-4fbf-98be-a5dcfa329c5a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 481beb69d2c4729bb2a030d257e802598131ea00
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088878"
---
# <a name="iremotedebugapplicationthreadgetstate"></a>IRemoteDebugApplicationThread::GetState
Získá stav tohoto vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetState(  
   DWORD*  pState  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pState`  
 [out] Kombinace následující příznaky stavu vlákna:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|THREAD_STATE_RUNNING|0x00000001|Vlákno je spuštěno.|  
|THREAD_STATE_SUSPENDED|0x00000002|Vlákno je pozastaveno.|  
|THREAD_BLOCKED|0x00000004|Je vlákno blokované.|  
|THREAD_OUT_OF_CONTEXT|0x00000008|Vlákno je obsahu.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte stav tohoto vlákna.  
  
## <a name="see-also"></a>Viz také  
 [IRemoteDebugApplicationThread – rozhraní](../../winscript/reference/iremotedebugapplicationthread-interface.md)