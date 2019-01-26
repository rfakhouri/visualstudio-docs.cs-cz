---
title: IDebugEngineProgram2::WatchForThreadStep | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5d144d02a34052cc06e5f63df75a2a7db3be4887
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54984012"
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
Sleduje spuštění (nebo zastavení sledování provádění) v dané vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WatchForThreadStep(   
   IDebugProgram2* pOriginatingProgram,  
   DWORD           dwTid,  
   BOOL            fWatch,  
   DWORD           dwFrame  
);  
```  
  
```csharp  
int WatchForThreadStep(   
   IDebugProgram2 pOriginatingProgram,  
   uint           dwTid,  
   int            fWatch,  
   uint           dwFrame  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pOriginatingProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt představující program se stupňovitým.  
  
 `dwTid`  
 [in] Určuje identifikátor vlákna, které chcete sledovat.  
  
 `fWatch`  
 [in] Nenulová (`TRUE`) znamená, že spuštění sledování pro spuštění ve vlákně identifikovaný `dwTid`; v opačném případě nula (`FALSE`) znamená, že zastavit sledování pro spuštění na `dwTid`.  
  
 `dwFrame`  
 [in] Určuje index snímku, který určuje typ kroku. Není-li hodnota je nula (0), typ kroku je "Krokovat s vnořením" a program by se měla zastavit pokaždé, když identifikované vlákna `dwTid` spustí. Když `dwFrame` je nenulová, typ kroku je "Krokovat přes" a program by se měla zastavit jenom v případě, že identifikované vlákna `dwTid` běží v objektu frame, jejíž index je větší než do zásobníku nebo `dwFrame`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když správce ladění relace (SDM) kroky program identifikován `pOriginatingProgram` parametr, upozorní všech ostatních připojených programů po zavolání metody.  
  
 Tato metoda se vztahuje pouze na stejném vlákně krokování.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)