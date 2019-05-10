---
title: TYPE_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TYPE_INFO
helpviewer_keywords:
- TYPE_INFO structure
ms.assetid: d725cb68-a565-49d1-a16f-ff0445c587a0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bbb64acfd71a6208fde3a5c3f84d6c5886ece72f
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460742"
---
# <a name="typeinfo"></a>TYPE_INFO
Tato struktura určuje různé druhy informací o typu pole.

## <a name="syntax"></a>Syntaxe

```cpp
struct _tagTYPE_INFO_UNION {
   dwTYPE_KIND dwKind;
   union {
      METADATA_TYPE typeMeta;
      PDB_TYPE      typePdb;
      BUILT_TYPE    typeBuilt;
      DWORD         unused;
   } type;
} TYPE_INFO;
```

```csharp
public struct TYPE_INFO {
   public uint   dwKind;
   public IntPtr unionmember;
};
```

## <a name="members"></a>Členové
 `dwKind`\
 Hodnota z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet, který určuje, jak interpretovat sjednocení.

 `type.typeMeta`\

 [C++ pouze] Obsahuje [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) strukturu Pokud `dwKind` je `TYPE_KIND_METADATA`.

 `type.typePdb`\

 [C++ pouze] Obsahuje [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) strukturu Pokud `dwKind` je `TYPE_KIND_PDB`.

 `type.typeBuilt`\

 [C++ pouze] Obsahuje [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) strukturu Pokud `dwKind` je `TYPE_KIND_BUILT`.

 `type.unused`\
 Nepoužité odsazení.

 `type`\
 Název sjednocení.

 `unionmember`\

 [C# pouze] Zařazování tuto hodnotu na typ odpovídající struktury na základě `dwKind`.

## <a name="remarks"></a>Poznámky
 Tato struktura je předán [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) metody, kde je vyplněna. Jak interpretovat obsah struktury je založen na `dwKind` pole.

> [!NOTE]
> [C++ pouze] Pokud `dwKind` rovná `TYPE_KIND_BUILT`, pak je nutné uvolnit základní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu při ničení `TYPE_INFO` struktury. To se provádí voláním `typeInfo.type.typeBuilt.pUnderlyingField->Release()`.

 [C# pouze] Následující tabulka ukazuje, jak interpretovat `unionmember` člen pro každý druh typu. Příklad ukazuje, jak to lze provést jednoho druhu typu.

|`dwKind`|`unionmember` interpretováno jako|
|--------------|----------------------------------|
|`TYPE_KIND_METADATA`|[METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)|
|`TYPE_KIND_PDB`|[PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)|
|`TYPE_KIND_BUILT`|[BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)|

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak interpretovat `unionmember` člena `TYPE_INFO` struktura v jazyce C#. Tento příklad ukazuje interpretace pouze jeden typ (`TYPE_KIND_METADATA`) ale ostatní jsou interpretovány stejným způsobem.

```csharp
using System;
using System.Runtime.Interop.Services;
using Microsoft.VisualStudio.Debugger.Interop;

namespace MyPackage
{
    public class MyClass
    {
        public void Interpret(TYPE_INFO ti)
        {
            if (ti.dwKind == (uint)enum_dwTypeKind.TYPE_KIND_METADATA)
            {
                 METADATA_TYPE dataType = (METADATA_TYPE)Marshal.PtrToStructure(ti.unionmember,
                                               typeof(METADATA_TYPE));
            }
        }
    }
}
```

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
- [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)
- [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)
- [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)
- [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)