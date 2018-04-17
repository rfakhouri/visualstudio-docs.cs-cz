---
title: BP_RESOLUTION_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_RESOLUTION_INFO
helpviewer_keywords:
- BP_RESOLUTION_INFO structure
ms.assetid: ba0c162a-61e8-4a0b-811f-4c1d8a5d82f0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0e163daff6466f9cc6e0f83fff20b89006a73dcc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="bpresolutioninfo"></a>BP_RESOLUTION_INFO
Popisuje informace vázané breakpoint zarážku kódu nebo zarážku data.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _BP_RESOLUTION_INFO {   
   BPRESI_FIELDS          dwFields;  
   BP_RESOLUTION_LOCATION bpResLocation;  
   IDebugProgram2*        pProgram;  
   IDebugThread2*         pThread;  
} BP_RESOLUTION_INFO;  
```  
  
```csharp  
public struct BP_RESOLUTION_INFO {   
   public uint                   dwFields;  
   public BP_RESOLUTION_LOCATION bpResLocation;  
   public IDebugProgram2         pProgram;  
   public IDebugThread2          pThread;  
};  
```  
  
## <a name="members"></a>Členové  
 `dwFields`  
 Kolekce příznaky z [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md) výčty, které určuje pole, která jsou vyplněna.  
  
 `bpResLocation`  
 [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) struktura, která určuje umístění zarážce kód nebo data.  
  
 `pProgram`  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který představuje aplikaci, v němž došlo k chybě zarážek.  
  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákno, ve kterém je spuštěna aplikace, která obsahuje chybu zarážek.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácen rutinou [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)   
 [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)   
 [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)