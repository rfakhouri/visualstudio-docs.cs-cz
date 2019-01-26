---
title: IDebugEventCallback2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEventCallback2
helpviewer_keywords:
- IDebugEventCallback2
ms.assetid: 2c935ee0-2e22-4be0-a852-73736f33c8c9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cdc20711d168a25ee28dde04849369a752fdb74a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54988087"
---
# <a name="idebugeventcallback2"></a>IDebugEventCallback2
Toto rozhraní používá ladicí stroj (DE) k odesílání událostí ladění do Správce ladění relace (SDM).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEventCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] implementuje toto rozhraní přijímat události z ladicího stroje.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Ladicí stroj obvykle obdrží toto rozhraní, když volá SDM [připojit](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md), nebo [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md). Ladicí stroj odesílá události do SDM voláním [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugEventCallback2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)|Odešle oznámení o události do SDM ladění.|  
  
## <a name="remarks"></a>Poznámky  
 I když [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) a [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) určit, že se mít `IDebugEventCallback2` rozhraní, se nejedná o případ a ukazatel rozhraní bude vždy hodnotu null. Místo toho musíte použít modul ladění `IDebugEventCallback2` rozhraní obdrželi volání [připojit](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md), nebo [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Pokud balíček implementuje [IDebugEventCallback](../../../extensibility/debugger/reference/idebugeventcallback2.md) ve spravovaném kódu, se důrazně doporučuje, který <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> vyvolat na různá rozhraní, které jsou předány [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Připojení](../../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)