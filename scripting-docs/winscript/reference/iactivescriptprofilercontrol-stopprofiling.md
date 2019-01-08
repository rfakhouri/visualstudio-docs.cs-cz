---
title: IActiveScriptProfilerControl::StopProfiling | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.StopProfiling
apilocation:
- scrobj.dll
ms.assetid: 23b46ed6-a398-44c0-bc49-bf122e697cfe
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b65c536c303a9bc0da7d0e29992315c05a61de52
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092479"
---
# <a name="iactivescriptprofilercontrolstopprofiling"></a>IActiveScriptProfilerControl::StopProfiling
Zastaví profilaci na skriptovacím stroji. Tato metoda volá [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md) na objekt profileru a pak ho uvolní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT StopProfiling(  
    [in] HRESULT hrShutdownReason);  
```  
  
#### <a name="parameters"></a>Parametry  
 `hrShutdownReason`  
 [in] Hodnota HRESULT se mají předat jako parametr [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md) metodu objektu profileru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|Profilace není povolená.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerControl – rozhraní](../../winscript/reference/iactivescriptprofilercontrol-interface.md)