---
title: PROVIDER_PROCESS_DATA | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROVIDER_PROCESS_DATA
helpviewer_keywords:
- PROVIDER_PROCESS_DATA structure
ms.assetid: ec2362ed-4a0c-4a09-9d66-8ff04e4f41ee
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d4013cabe43693e52498a3094aee10e4786da43a
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460795"
---
# <a name="providerprocessdata"></a>PROVIDER_PROCESS_DATA
Tato struktura poskytuje informace o procesech spuštěných na počítači.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagPROVIDER_PROCESS_DATA {
   PROVIDER_FIELDS    Fields;
   PROGRAM_NODE_ARRAY ProgramNodes;
   BOOL               fIsDebuggerPresent;
} PROVIDER_PROCESS_DATA;
```

```csharp
public struct PROVIDER_PROCESS_DATA {
   public uint               Fields;
   public PROGRAM_NODE_ARRAY ProgramNodes;
   public int                fIsDebuggerPresent;
}
```

## <a name="members"></a>Členové
 `Fields`\
 Kombinace příznaků z [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md) výčet určující, která pole jsou vyplněna.

 `ProgramNodes`\
 A [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) strukturu, která obsahuje celou řadu uzly programů.

 `fIsDebuggerPresent`\
 Nenulová (`TRUE`) Pokud [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladicí program je spuštěn, nula (`FALSE`) Pokud není.

## <a name="remarks"></a>Poznámky
 Tato struktura je předán [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) metody, kde je vyplněna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md)
- [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)