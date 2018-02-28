---
title: IDebugEngineProgram2::WatchForThreadStep | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 3ca2e5eff223a22a3359f6fc4a391d2102f31b67
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
Sleduje provádění (nebo zastaví sledování pro spouštění) pro dané vlákno.  
  
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
 [v] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt reprezentující program se stupeň.  
  
 `dwTid`  
 [v] Určuje identifikátor vlákno, které chcete sledovat.  
  
 `fWatch`  
 [v] Nenulová (`TRUE`) znamená sledování pro spuštění ve vlákně identifikovaný spustí `dwTid`, jinak hodnota nula (`FALSE`) znamená ukončit sledování pro spuštění na `dwTid`.  
  
 `dwFrame`  
 [v] Určuje index rámečku, který určuje typ kroku. Je-li hodnota je nula (0), typ kroku je "krok do" a program by se měla zastavit, vždy, když vlákno se identifikovanou pomocí `dwTid` provede. Když `dwFrame` je nulová, typ kroku je "Krok přes" a tento program by se měla zastavit jenom v případě, že vlákno identifikovaný `dwTid` běží v rámci jejichž index je rovna nebo vyšší v zásobníku než `dwFrame`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když správce ladicí relace (SDM) kroky program, identifikovaný `pOriginatingProgram` parametr upozorní všech ostatních připojených programy voláním této metody.  
  
 Tato metoda se vztahuje pouze na stejném vlákně krokování.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)