---
title: IDebugProgram3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProgram3 interface
ms.assetid: 4301ba23-c00c-4ce5-8b1e-3f27da312034
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5849617b1fb0d1446b847f9eb5137de06b685953
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53896605"
---
# <a name="idebugprogram3"></a>IDebugProgram3
Toto rozhraní představuje program, který běží v procesu a rozšiřuje [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md) tím, že poskytuje informace o vláknech.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgram3 : IDebugProgram3  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) a vlastní port dodavatele implementovat toto rozhraní k reprezentaci programu v procesu. Správce ladění relace (SDM) také implementuje toto rozhraní poskytnout informace o [připojit](../../../extensibility/debugger/reference/idebugprogram2-attach.md).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událost vrátí toto rozhraní pro nový program. Toto rozhraní je také použít jako parametr pro mnoho metod na více rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugProgram3`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ExecuteOnThread](../../../extensibility/debugger/reference/idebugprogram3-executeonthread.md)|Spustí program. Vlákno se vrátí do poskytnout informace o ladicího programu, ve které vlákno je uživatel zobrazení při provádění.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="remarks"></a>Poznámky  
 Program je kontejner vlákna spuštěná v konkrétní za běhu architektury, zatímco proces se skládá z jednoho nebo více programů.  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)   
 [Další](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)   
 [Události](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)