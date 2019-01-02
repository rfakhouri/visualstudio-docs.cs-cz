---
title: PENDING_BP_STATE_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- PENDING_BP_STATE_INFO
helpviewer_keywords:
- PENDING_BP_STATE_INFO structure
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 93b1278c9f0bc11ce4a79e10750f4f7952fba81f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53896042"
---
# <a name="pendingbpstateinfo"></a>PENDING_BP_STATE_INFO
Obsahuje informace o stavu, který je připravený k připojení k umístění kódu zarážku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagPENDING_BP_STATE_INFO {   
   PENDING_BP_STATE       state;  
   PENDING_BP_STATE_FLAGS flags;  
} PENDING_BP_STATE_INFO;  
```  
  
```csharp  
public struct PENDING_BP_STATE_INFO {   
   public uint state;  
   public uint flags;  
};  
```  
  
## <a name="members"></a>Členové  
 state  
 Hodnota z [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md) výčet, který určuje stav čekající zarážka.  
  
 příznaky  
 Kombinace příznaků z [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md) výčet, který určuje, zda je virtualizovaný zarážku.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předán [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md) metody, kde je vyplněna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)   
 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)   
 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)