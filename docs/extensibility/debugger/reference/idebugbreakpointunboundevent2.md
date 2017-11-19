---
title: IDebugBreakpointUnboundEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBreakpointUnboundEvent2
helpviewer_keywords: IDebugBreakpointUnboundEvent2
ms.assetid: 6b1e1863-0c64-4d85-8ab9-aface522fdea
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa2e9e50205a400616bf71d0e60d60f4a826bdb6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbreakpointunboundevent2"></a>IDebugBreakpointUnboundEvent2
Toto rozhraní informuje správce ladicí relace (SDM) vázané breakpoint byl není svázána s načíst program.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBreakpointUnboundEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní jako součást své podpory zarážky. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní (SDM používá [QueryInterface](/cpp/atl/queryinterface) pro přístup k `IDebugEvent2` rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí bylo vázané breakpoint nevázaný. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytl SDM, pokud je připojené k programu laděné funkce zpětného volání.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugBreakpointUnboundEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)|Získá zarážek, která se aktivovala nevázaný.|  
|[Getreason –](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)|Získá důvod, proč nevázaný zarážce.|  
  
## <a name="remarks"></a>Poznámky  
 Při uvolnění modul ladění knihoven DLL nebo třídu, musí být všechny zarážky, které byly vázány na kód v tomto modulu není svázána s programu laděné. `IDebugBreakpointUnboundEvent2` Je odeslán pro každé nevázaný zarážky.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)