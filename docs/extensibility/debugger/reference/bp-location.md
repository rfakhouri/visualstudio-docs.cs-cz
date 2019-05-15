---
title: BP_LOCATION | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_LOCATION
helpviewer_keywords:
- BP_LOCATION union
ms.assetid: ed1e874c-f289-4c31-8b6c-04dde03ad0f5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 94e731b56bf5c7554edf11620435cd24778e8e9d
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615354"
---
# <a name="bplocation"></a>BP_LOCATION
Určuje typ struktury, na které se používají k popisu umístění zarážky.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _BP_LOCATION {
    BP_LOCATION_TYPE bpLocationType;
    union {
        BP_LOCATION_CODE_FILE_LINE   bplocCodeFileLine;
        BP_LOCATION_CODE_FUNC_OFFSET bplocCodeFuncOffset;
        BP_LOCATION_CODE_CONTEXT     bplocCodeContext;
        BP_LOCATION_CODE_STRING      bplocCodeString;
        BP_LOCATION_CODE_ADDRESS     bplocCodeAddress;
        BP_LOCATION_DATA_STRING      bplocDataString;
        BP_LOCATION_RESOLUTION       bplocResolution;
        DWORD                        unused;
    } bpLocation;
} BP_LOCATION;
```

```csharp
public struct BP_LOCATION {
    public uint   bpLocationType;
    public IntPtr unionmember1;
    public IntPtr unionmember2;
    public IntPtr unionmember3;
    public IntPtr unionmember4;
};
```

## <a name="members"></a>Členové
`bpLocationType`\
Hodnota z [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) výčet použité k interpretaci `bpLocation` sjednocení nebo `unionmemberX` členy.

`bpLocation`.`bplocCodeFileLine`\
[C++ pouze] Obsahuje [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) strukturu Pokud `bpLocationType`  =  `BPLT_CODE_FILE_LINE`.

`bpLocation.bplocCodeFuncOffset`\
[C++ pouze] Obsahuje [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) strukturu Pokud `bpLocationType`  =  `BPLT_CODE_FUNC_OFFSET`.

`bpLocation.bplocCodeContext`\
[C++ pouze] Obsahuje [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md) strukturu Pokud `bpLocationType`  =  `BPLT_CODE_CONTEXT`.

`bpLocation.bplocCodeString`\
[C++ pouze] Obsahuje [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md) strukturu Pokud `bpLocationType`  =  `BPLT_CODE_STRING`.

`bpLocation.bplocCodeAddress`\
[C++ pouze] Obsahuje [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md) strukturu Pokud `bpLocationType`  =  `BPLT_CODE_ADDRESS`.

`bpLocation.bplocDataString`\
[C++ pouze] Obsahuje [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md) strukturu Pokud `bpLocationType`  =  `BPLT_DATA_STRING`.

`bpLocation.bplocResolution`\
[C++ pouze] Obsahuje [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md) strukturu Pokud `bpLocationType`  =  `BPLT_RESOLUTION`.

`unionmember1`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

`unionmember2`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

`unionmember3`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

`unionmember4`\
[C# pouze] Viz poznámky o tom, jak interpretovat.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.

 [C# pouze] `unionmemberX` Členy se interpretují podle následující tabulky. Podívejte se dolů levém sloupci `bpLocationType` hodnotu pak nahlédnout další sloupce, které chcete zjistit, co jednotlivé `unionmemberX` člen představuje a zařazování `unionmemberX` odpovídajícím způsobem. Podívejte se na příklad pro způsob, jak interpretovat součástí tato struktura v jazyce C#.

|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|
|----------------------|--------------------|--------------------|--------------------|--------------------|
|`BPLT_CODE_FILE_LINE`|`string` (místní)|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|-|-|
|`BPLT_CODE_FUNC_OFFSET`|`string` (místní)|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|-|-|
|`BPLT_CODE_CONTEXT`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|
|`BPLT_CODE_STRING`|`string` (místní)|`string` (podmíněný výraz)|-|-|
|`BPLT_CODE_ADDRESS`|`string` (místní)|`string` (adresa URL modulu)|`string` (název funkce)|`string` (adresa)|
|`BPLT_DATA_STRING`|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|`string` (místní)|`string` (výraz data)|`uint` (počet prvků)|
|`BPLT_RESOLUTION`|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|-|-|-|

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak interpretovat `BP_LOCATION` struktura v jazyce C# pro `BPLT_DATA_STRING` typu. Tento konkrétní typ ukazuje, jak interpretovat všechny čtyři `unionmemberX` členy ve všech možných formátů (objektu, řetězce a číslo).

```csharp
using System;
using System.Runtime.Interop.Services;
using Microsoft.VisualStudio.Debugger.Interop;

namespace MyPackage
{
    public class MyClass
    {
        public void Interpret(BP_LOCATION bp)
        {
            if (bp.bpLocationType == (uint)enum_BP_LOCATION_TYPE.BPLT_DATA_STRING)
            {
                IDebugThread2 pThread = (IDebugThread2)Marshal.GetObjectForIUnknown(bp.unionmember1);
                string context = Marshal.PtrToStringBSTR(bp.unionmember2);
                string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);
                uint numElements = (uint)Marshal.ReadInt32(bp.unionmember4);
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
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)
- [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)
- [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md)
- [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md)
- [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md)
- [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md)
- [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md)
