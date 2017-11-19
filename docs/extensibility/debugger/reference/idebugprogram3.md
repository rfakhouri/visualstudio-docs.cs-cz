---
title: IDebugProgram3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProgram3 interface
ms.assetid: 4301ba23-c00c-4ce5-8b1e-3f27da312034
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2da4dcb4911488bd82c358efc3b8075f1941af6f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogram3"></a>IDebugProgram3
Toto rozhraní představuje program, který běží v procesu a rozšiřuje [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md) tím, že poskytuje informace o přístup z více vláken.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgram3 : IDebugProgram3  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) a vlastní port dodavatele implementovat toto rozhraní představují program v procesu. Správce ladicí relace (SDM) také implementuje toto rozhraní poskytovat informace o [Attach](../../../extensibility/debugger/reference/idebugprogram2-attach.md).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událostí vrátí toto rozhraní pro nový program. Toto rozhraní je také použít jako parametr pro mnoho způsobů na více rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugProgram3`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ExecuteOnThread](../../../extensibility/debugger/reference/idebugprogram3-executeonthread.md)|Spustí program. Vlákno je vrácen do poskytnout ladicí program informace, na které vlákno je uživatel zobrazení při provádění.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="remarks"></a>Poznámky  
 Program je spuštěn v konkrétní architektuře běhu a proces se skládá z jednoho nebo více programů kontejner přístup z více vláken.  
  
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