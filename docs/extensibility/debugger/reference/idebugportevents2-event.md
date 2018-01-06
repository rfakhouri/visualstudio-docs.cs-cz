---
title: IDebugPortEvents2::Event | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortEvents2::Event
helpviewer_keywords: IDebugPortEvents2::Event
ms.assetid: 5cc813f7-04a1-4462-9ea7-fbddcf0e0143
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6713e8a85f9d4078a920be023438307146cbafdb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportevents2event"></a>IDebugPortEvents2::Event
Tato metoda odesílá události, které označuje vytvoření a zničení procesy a programy na portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Event(  
   IDebugCoreServer2* pServer,  
   IDebugPort2*       pPort,  
   IDebugProcess2*    pProcess,  
   IDebugProgram2*    pProgram,  
   IDebugEvent2*      pEvent,  
   REFIID             riidEvent  
);  
```  
  
```csharp  
int Event(  
   IDebugCoreServer2 pServer,   
   IDebugPort2       pPort,   
   IDebugProcess2    pProcess,   
   IDebugProgram2    pProgram,   
   IDebugEvent2      pEvent,   
   ref Guid          riidEvent  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMachine`  
 [v] [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) objekt, který reprezentuje server, ladění (jeden pro každou instanci [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]) ve kterém došlo k události.  
  
 `pPort`  
 [v] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) objekt, který představuje port, ve kterém došlo k události.  
  
 `pProcess`  
 [v] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt, který představuje proces, ve kterém došlo k události.  
  
 `pProgram`  
 [v] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který představuje program, ve kterém došlo k události.  
  
 `pEvent`  
 [v] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) objekt, který identifikuje událost. Možné události jsou následující:  
  
-   [IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)  
  
-   [IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)  
  
-   [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
-   [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)  
  
 `riidEvent`  
 [v] Identifikátor GUID této události. Vzhledem k tomu, že událost je přetypovat na [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) před voláním této metody, tento identifikátor je snazší zjistit, jaké události jsou odesílány.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)