---
title: IDebugBoundBreakpoint2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBoundBreakpoint2
helpviewer_keywords:
- IDebugBoundBreakpoint2 interface
ms.assetid: df33c52e-ded2-48a0-951d-1f36c8fc922e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6ce63ce7f7d6a4f438c0e9f622c34a2231afd6ef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2"></a>IDebugBoundBreakpoint2
Toto rozhraní představuje zarážku s vazbou na umístění kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBoundBreakpoint2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní jako součást své podpory zarážky.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [vazby](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) vytvoří toto rozhraní. Volání [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md) a [Další](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) můžete také získat toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugBoundBreakpoint2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|Získá čekající zarážek, ze kterého byl vytvořen zadaný vázané breakpoint.|  
|[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|Získá stav této vázané breakpoint.|  
|[GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)|Získá aktuální počet přístupů pro tento vázané breakpoint.|  
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|Získá zarážek řešení, která popisuje tuto zarážek.|  
|[Povolit](../../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|Povolí nebo zakáže bod přerušení.|  
|[SetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-sethitcount.md)|Nastaví počet přístupů k této vázané breakpoint.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)|Nastaví nebo změny přidružené k této vázané breakpoint podmínku.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)|Nastaví nebo změňte počet průchodu přidružené k této vázané breakpoint.|  
|[Odstranit](../../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|Odstraní zarážku.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)   
 [Další](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)   
 [Vazby](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)