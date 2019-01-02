---
title: IDebugEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ca850f06fa2c17bb6f7c6ccb0756ad2498c67b9d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53870161"
---
# <a name="idebugevent2"></a>IDebugEvent2
Toto rozhraní se používá ke komunikaci důležitých informací o ladění, jako je například pozastavení na zarážce a méně důležité informace, jako je například zprávu ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) a vlastní port dodavatele implementovat toto rozhraní na stejný objekt jako všechny ostatní události rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Pomocí rozhraní argument ID (IID) k [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) nebo [události](../../../extensibility/debugger/reference/idebugportevents2-event.md), Správce ladění relace (SDM) volá [QueryInterface](/cpp/atl/queryinterface) na `IDebugEvent2` rozhraní získat rozhraní odpovídající události.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Získá atributy pro tuto událost ladění.|  
  
## <a name="remarks"></a>Poznámky  
 Konkrétnější události rozhraní, jako například [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), není odvozen z rozhraní IDebugEvent2, ale místo toho jsou implementované jako samostatné rozhraní na stejný objekt jako `IDebugEvent2`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Události](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)