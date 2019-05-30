---
title: BP_RESOLUTION_LOCATION | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_LOCATION
helpviewer_keywords:
- BP_RESOLUTION_LOCATION structure
ms.assetid: 21dc5246-69c1-43e3-855c-9cd4e596c0e6
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ed287f2d90e1ee92c7e0fd4ae685fbb9f38854f4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350587"
---
# <a name="bpresolutionlocation"></a>BP_RESOLUTION_LOCATION
Určuje strukturu řešení umístění zarážky.

## <a name="syntax"></a>Syntaxe

```cpp
struct _BP_RESOLUTION_LOCATION {
    BP_TYPE bpType;
    union {
        BP_RESOLUTION_CODE bpresCode;
        BP_RESOLUTION_DATA bpresData;
        int                unused;
    } bpResLocation;
} BP_RESOLUTION_LOCATION;
```

```csharp
public struct BP_RESOLUTION_LOCATION {
    public uint   bpType;
    public IntPtr unionmember1;
    public IntPtr unionmember2;
    public IntPtr unionmember3;
    public uint   unionmember4;
};
```

## <a name="members"></a>Členové
`bpType`\
Hodnota z [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) výčet, který určuje, jak interpretovat `bpResLocation` sjednocení nebo `unionmemberX` členy.

`bpResLocation.bpresCode`\
[C++ pouze] Obsahuje [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md) strukturu Pokud `bpType`  =  `BPT_CODE`.

`bpResLocation.bpresData`\
[C++ pouze] Obsahuje [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) strukturu Pokud `bpType`  =  `BPT_DATA`.

`bpResLocation.unused`\
[C++ pouze] Zástupný symbol.

`unionmember1`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

`unionmember2`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

`unionmember3`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

`unionmember4`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) a [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktury.

 [C# pouze] `unionmemberX` Členy se interpretují podle následující tabulky. Podívejte se dolů levém sloupci `bpType` hodnoty napříč pak určit, co každý `unionmemberX` člen představuje a zařazování `unionmemberX` odpovídajícím způsobem. Podívejte se na příklad pro způsob, jak interpretovat tato struktura v jazyce C#.

|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|
|----------------------|--------------------|--------------------|--------------------|--------------------|
|`BPT_CODE`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|
|`BPT_DATA`|`string` (výraz data)|`string` (název funkce)|`string` (název image)|`enum_BP_RES_DATA_FLAGS`|

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak interpretovat `BP_RESOLUTION_LOCATION` struktura v jazyce C#.

```csharp
using System;
using System.Runtime.Interop.Services;
using Microsoft.VisualStudio.Debugger.Interop;

namespace MyPackage
{
    public class MyClass
    {
        public void Interpret(BP_RESOLUTION_LOCATION bprl)
        {
            if (bprl.bpType == (uint)enum_BP_TYPE.BPT_CODE)
            {
                IDebugCodeContext2 pContext = (IDebugCodeContext2)Marshal.GetObjectForIUnknown(bp.unionmember1);
            }
            else if (bprl.bpType == (uint)enum_BP_TYPE.BPT_DATA)
            {
                string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);
                string functionName = Marshal.PtrToStringBSTR(bp.unionmember2);
                string imageName = Marshal.PtrToStringBSTR(bp.unionmember3);
                enum_BP_RES_DATA_FLAGS numElements = (enum_BP_RES_DATA_FLAGS)bp.unionmember4;
            }
        }
    }
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)
- [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)
- [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md)
