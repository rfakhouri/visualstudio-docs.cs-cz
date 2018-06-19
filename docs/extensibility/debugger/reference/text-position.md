---
title: TEXT_POSITION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- TEXT_POSITION
helpviewer_keywords:
- TEXT_POSITION structure
ms.assetid: 6dcec574-a852-49fa-8c2e-2e71cbb5e3c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e910de3682486d56e66125ad1f6c02ea0a14a55b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126992"
---
# <a name="textposition"></a>TEXT_POSITION
Popisuje umístění, řádku a ve sloupci v zadaném textu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagTEXT_POSITION {   
   DWORD dwLine;  
   DWORD dwColumn;  
} TEXT_POSITION;  
```  
  
```csharp  
public struct TEXT_POSITION {   
   public uint dwLine;  
   public uint dwColumn;  
};  
```  
  
## <a name="members"></a>Členové  
 dwLine  
 Index řádku ve zdrojovém souboru.  
  
 dwColumn  
 Znak posun v souladu.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je používán [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) a [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktury.  
  
 Tato struktura je vyplněna objektem volání těchto metod:  
  
-   [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)  
  
-   [Getsourcerange –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)  
  
-   [Getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)  
  
-   [Getoffset –](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)  
  
 Tato struktura je jako parametr předaný následujících metod:  
  
-   [GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)  
  
-   [onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)  
  
-   [onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)  
  
-   [onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)  
  
-   [onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)   
 [Getsourcerange –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)   
 [Getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)   
 [Getoffset –](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)   
 [GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)