---
title: IDebugBreakpointEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointEvent2
helpviewer_keywords:
- IDebugBreakpointEvent2 interface
ms.assetid: 50b3a7a7-331b-42c8-922c-ff3522ebe1da
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1e6a6ecfd5a099ab6f532509438dadd63b49ee27
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53960599"
---
# <a name="idebugbreakpointevent2"></a>IDebugBreakpointEvent2
Ladicí stroj (DE) pošle toto rozhraní Správce ladění relace (SDM), když program zastaví na zarážce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBreakpointEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní jako součást jeho podporu pro zarážky. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) musí implementovat rozhraní na stejný objekt jako toto rozhraní (SDM používá [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událost, když jeden zarážky v programu. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytnutých SDM při připojení k laděnému programu funkce zpětného volání.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugBreakpointEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)|Vytvoří čítač pro všechny zarážky, které aktivuje na aktuální umístění v kódu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)