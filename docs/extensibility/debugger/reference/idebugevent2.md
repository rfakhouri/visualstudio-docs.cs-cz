---
title: IDebugEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0d783cb13ee227e317afe9b49abedb6f53e9fa76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugevent2"></a>IDebugEvent2
Toto rozhraní se používá ke komunikaci kritické ladicí informace, jako je například pozastavení na zarážce a méně důležité informace, například zprávu ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladění modulu (DE) a vlastní port dodavatele toto rozhraní implementovat na stejný objekt jako všechny ostatní události rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Pomocí rozhraní argument ID (IID) zadané [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) nebo [událostí](../../../extensibility/debugger/reference/idebugportevents2-event.md), volá správce ladicí relace (SDM) [QueryInterface](/cpp/atl/queryinterface) na `IDebugEvent2` rozhraní k získání rozhraní příslušné události.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Získá atributy pro tuto událost ladění.|  
  
## <a name="remarks"></a>Poznámky  
 Více konkrétních událostí rozhraní, jako například [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), není odvozen z rozhraní IDebugEvent2, ale místo toho jsou implementované jako samostatné rozhraní na stejný objekt jako `IDebugEvent2`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Události](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)