---
title: IActiveScriptProfilerControl::StartProfiling | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.StartProfiling
apilocation:
- scrobj.dll
ms.assetid: 56a7b3b7-8c21-43d0-9d8b-53bbc19fabb9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5362eaba439ff7a645a8323c4eed5d9496f6d88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793560"
---
# <a name="iactivescriptprofilercontrolstartprofiling"></a>IActiveScriptProfilerControl::StartProfiling
Spustí se profilace na skriptovacího stroje. Skriptovací stroj vytvoří instanci objektu profileru tím, že zavoláte na [CoCreateInstance](http://msdn.microsoft.com/en-us/7295a55b-12c7-4ed0-a7a4-9ecee16afdec).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT StartProfiling(  
    [in] REFCLSID clsidProfilerObject,  
    [in] DWORD dwEventMask,  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>Parametry  
 `clsidProfilerObject`  
 [v] Třídy identifikátor (CLSID) profileru objektu, který se má vytvořit.  
  
 `dwEventMask`  
 [v] 4bajtový bitová maska, která určuje typy událostí. Službu bits jsou definovány v [PROFILER_EVENT_MASK – výčet](../../winscript/reference/profiler-event-mask-enumeration.md).  
  
 `dwContext`  
 [v] 4bajtový hodnotu, která je předaný objekt profileru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`ACTIVPROF_E_PROFILER_PRESENT`|Profilace je již povolen.|  
  
## <a name="see-also"></a>Viz také  
 [Iactivescriptprofilercontrol – rozhraní](../../winscript/reference/iactivescriptprofilercontrol-interface.md)