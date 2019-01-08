---
title: IActiveScriptProfilerControl::SetProfilerEventMask | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.SetProfilerEventMask
apilocation:
- scrobj.dll
ms.assetid: 207e192f-e12e-4fcb-b4d8-eaee50ecb86e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45ded6caec95f5421328be09e299af535765a9c2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086785"
---
# <a name="iactivescriptprofilercontrolsetprofilereventmask"></a>IActiveScriptProfilerControl::SetProfilerEventMask
Nastaví na 4 bajty. bitová maska, která určuje typy událostí, které by měla vyvolat skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetProfilerEventMask(  
    [in] DWORD dwEventMask);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwEventMask`  
 [in] 4bajtový bitová maska, která určuje typy událostí. Bity jsou definovány v [profiler_event_mask – výčet](../../winscript/reference/profiler-event-mask-enumeration.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|Profilace není povolená.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerControl – rozhraní](../../winscript/reference/iactivescriptprofilercontrol-interface.md)