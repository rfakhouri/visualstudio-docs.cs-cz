---
title: BP_RESOLUTION_LOCATION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_RESOLUTION_LOCATION
helpviewer_keywords:
- BP_RESOLUTION_LOCATION structure
ms.assetid: 21dc5246-69c1-43e3-855c-9cd4e596c0e6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 032228596773d4a5a164f904c1caae161b693f64
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31106536"
---
# <a name="bpresolutionlocation"></a>BP_RESOLUTION_LOCATION
Určuje strukturu zarážek umístění řešení.  
  
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
   public uint bpType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public uint   unionmember4;  
};  
```  
  
## <a name="members"></a>Členové  
 `bpType`  
 Hodnota z [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) výčet, který určuje, jak interpretovat `bpResLocation` sjednocení nebo `unionmemberX` členy.  
  
 `bpResLocation.bpresCode`  
 [Pouze C++] Obsahuje [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md) struktury, pokud `bpType`  =  `BPT_CODE`.  
  
 `bpResLocation.bpresData`  
 [Pouze C++] Obsahuje [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) struktury, pokud `bpType`  =  `BPT_DATA`.  
  
 `bpResLocation.unused`  
 [Pouze C++] Zástupný symbol.  
  
 `unionmember1`  
 [C# pouze] V části poznámky o tom, jak interpretovat.  
  
 `unionmember2`  
 [C# pouze] V části poznámky o tom, jak interpretovat.  
  
 `unionmember3`  
 [C# pouze] V části poznámky o tom, jak interpretovat.  
  
 `unionmember4`  
 [C# pouze] V části poznámky o tom, jak interpretovat.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je členem skupiny [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) a [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktury.  
  
 [C# pouze] `unionmemberX` Členy se interpretují podle následující tabulky. Podívejte se levém sloupci pro `bpType` hodnotu napříč pak určit, co každý `unionmemberX` představuje člen a zařazování `unionmemberX` odpovídajícím způsobem. Podívejte se na příklad pro způsob, jak interpretovat tato struktura v jazyce C#.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPT_CODE`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPT_DATA`|`string` (výraz data)|`string` (název funkce)|`string` (název bitové kopie)|`enum_BP_RES_DATA_FLAGS`|  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak interpretovat `BP_RESOLUTION_LOCATION` struktury v jazyku C#.  
  
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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)   
 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)   
 [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md)