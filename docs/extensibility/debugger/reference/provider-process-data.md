---
title: PROVIDER_PROCESS_DATA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROVIDER_PROCESS_DATA
helpviewer_keywords:
- PROVIDER_PROCESS_DATA structure
ms.assetid: ec2362ed-4a0c-4a09-9d66-8ff04e4f41ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61b1b5d67faea0ce5c1c2a56b3f411cd4f947067
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="providerprocessdata"></a>PROVIDER_PROCESS_DATA
Tato struktura poskytuje informace o procesech spuštěných na počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagPROVIDER_PROCESS_DATA {  
   PROVIDER_FIELDS    Fields;  
   PROGRAM_NODE_ARRAY ProgramNodes;  
   BOOL               fIsDebuggerPresent;  
} PROVIDER_PROCESS_DATA;  
```  
  
```csharp  
public struct PROVIDER_PROCESS_DATA {  
   public uint               Fields;  
   public PROGRAM_NODE_ARRAY ProgramNodes;  
   public int                fIsDebuggerPresent;  
}  
```  
  
## <a name="members"></a>Členové  
 Pole  
 Kombinace příznaků z [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md) výčtu, která určuje, které jsou vyplněna.  
  
 ProgramNodes  
 A [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) struktura, která obsahuje pole program uzlů.  
  
 fIsDebuggerPresent  
 Nenulové hodnoty (`TRUE`) Pokud [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladicí program běží, nula (`FALSE`) Pokud není.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předána [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) metoda, kde je vyplněna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md)   
 [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)