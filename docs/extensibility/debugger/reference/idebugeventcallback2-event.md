---
title: IDebugEventCallback2::Event | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEventCallback2::Event
helpviewer_keywords: IDebugEventCallback2::Event
ms.assetid: e5a3345b-d460-4e40-8f5b-3111c56a2ed9
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0a7e5d4d20ae7e4409599a77250986b759f152fb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugeventcallback2event"></a>IDebugEventCallback2::Event
Odešle oznámení o události ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Event(   
   IDebugEngine2*  pEngine,  
   IDebugProcess2* pProcess,  
   IDebugProgram2* pProgram,  
   IDebugThread2*  pThread,  
   IDebugEvent2*   pEvent,  
   REFIID          riidEvent,  
   DWORD           dwAttrib  
);  
```  
  
```csharp  
int Event(   
   IDebugEngine2  pEngine,  
   IDebugProcess2 pProcess,  
   IDebugProgram2 pProgram,  
   IDebugThread2  pThread,  
   IDebugEvent2   pEvent,  
   ref Guid       riidEvent,  
   uint           dwAttrib  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pEngine`  
 [v] [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) objekt, který reprezentuje modul ladění (DE), který odesílá této události. K vyplnění tento parametr je vyžadován Zavedenými.  
  
 `pProcess`  
 [v] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt, který představuje proces, ve kterém dojde k události. Tento parametr je vyplněno správce ladicí relace (SDM). Zavedenými vždycky předá pro tento parametr hodnotu null.  
  
 `pProgram`  
 [v] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje program, ve kterém dojde k této události. Pro většinu události je tento parametr hodnotu null.  
  
 `pThread`  
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vláken, ve kterém dojde k této události. Pro zastavení události, tento parametr nemůže mít hodnotu null jako rámce zásobníku se získávají z tohoto parametru.  
  
 `pEvent`  
 [v] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) objekt, který reprezentuje ladění událostí.  
  
 `riidEvent`  
 [v] Identifikátor GUID, který identifikuje které událostí rozhraní získat z `pEvent` parametr.  
  
 `dwAttrib`  
 [v] Kombinace příznaků z [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md) výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Při volání této metody `dwAttrib` parametru musí odpovídat hodnotě vrácené [GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md) předaná metoda jako říká události objektu `pEvent` parametr.  
  
 Všechny události ladění jsou odeslány asynchronně, bez ohledu na to, zda je událost samotné asynchronní nebo ne. Když Zavedenými volá tuto metodu, návratovou hodnotu neindikuje zda zpracování události, pouze zda událost byla přijata. Ve skutečnosti ve většině situací, události nebyl zpracován po návratu tato metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)