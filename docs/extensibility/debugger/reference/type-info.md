---
title: TYPE_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TYPE_INFO
helpviewer_keywords: TYPE_INFO structure
ms.assetid: d725cb68-a565-49d1-a16f-ff0445c587a0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5dc77aa5b633c4160fc34717c0b9382d89d9f0e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="typeinfo"></a>TYPE_INFO
Tato struktura určuje různých typů informací o typu pole.  
  
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
  
#### <a name="parameters"></a>Parametry  
 dwKind  
 Hodnota z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet, který určuje, jak interpretovat sjednocení.  
  
 type.typeMeta  
 [Pouze C++] Obsahuje [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) struktury, pokud `dwKind` je `TYPE_KIND_METADATA`.  
  
 type.typePdb  
 [Pouze C++] Obsahuje [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) struktury, pokud `dwKind` je `TYPE_KIND_PDB`.  
  
 type.typeBuilt  
 [Pouze C++] Obsahuje [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) struktury, pokud `dwKind` je `TYPE_KIND_BUILT`.  
  
 Type.unused  
 Nepoužívané odsazení.  
  
 – typ  
 Název sjednocení.  
  
 unionmember  
 [C# pouze] Zařazování na typ odpovídající struktury na základě `dwKind`.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předána [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) metoda, kde je vyplněna. Jak se interpretují obsah strukturu je založena na `dwKind` pole.  
  
> [!NOTE]
>  [Pouze C++] Pokud `dwKind` rovná `TYPE_KIND_BUILT`, pak je nutné uvolnit základní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu při ničení `TYPE_INFO` struktura. To se provádí volání `typeInfo.type.typeBuilt.pUnderlyingField->Release()`.  
  
 [C# pouze] Následující tabulka ukazuje, jak interpretovat `unionmember` člena pro jednotlivé typy typu. Příklad ukazuje, jak to provést pro jeden druh typu.  
  
|`dwKind`|`unionmember`interpretovat jako|  
|--------------|----------------------------------|  
|`TYPE_KIND_METADATA`|[METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)|  
|`TYPE_KIND_PDB`|[PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)|  
|`TYPE_KIND_BUILT`|[BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)|  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak interpretovat `unionmember` členem `TYPE_INFO` struktury v jazyku C#. Tento příklad ukazuje interpretace pouze jeden typ (`TYPE_KIND_METADATA`), ale ostatní se interpretují stejným způsobem.  
  
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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)