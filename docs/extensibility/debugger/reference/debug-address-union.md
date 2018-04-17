---
title: DEBUG_ADDRESS_UNION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_ADDRESS_UNION
helpviewer_keywords:
- DEBUG_ADDRESS_UNION union
ms.assetid: e3d11aab-de0d-4109-b5dc-11e07e64382d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b0fcd662e3a4831b78ca55c139ce1511ea04b24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="debugaddressunion"></a>DEBUG_ADDRESS_UNION
Popisuje různé druhy adresy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS_UNION {  
   ADDRESS_KIND dwKind;  
   union {  
      NATIVE_ADDRESS                  addrNative;  
      UNMANAGED_ADDRESS_THIS_RELATIVE addrThisRel;  
      UNMANAGED_ADDRESS_PHYSICAL      addrUPhysical;  
      METADATA_ADDRESS_METHOD         addrMethod;  
      METADATA_ADDRESS_FIELD          addrField;  
      METADATA_ADDRESS_LOCAL          addrLocal;  
      METADATA_ADDRESS_PARAM          addrParam;  
      METADATA_ADDRESS_ARRAYELEM      addrArrayElem;  
      METADATA_ADDRESS_RETVAL         addrRetVal;  
      DWORD                           unused;  
   } addr;  
} DEBUG_ADDRESS_UNION;  
```  
  
```csharp  
public struct DEBUG_ADDRESS_UNION {  
   public ADDRESS_KIND dwKind;  
   public IntPtr       unionmember;  
}  
```  
  
## <a name="terms"></a>Podmínky  
 dwKind  
 Hodnota z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčtu, určíte, jak interpretovat sjednocení.  
  
 addr.addrNative  
 [Pouze C++] Obsahuje [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) struktury, pokud `dwKind` = ADDRESS_KIND_NATIVE.  
  
 addr.addrThisRel  
 [Pouze C++] Obsahuje[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) struktury, pokud `dwKind` = ADDRESS_KIND_UNMANAGED_THIS_RELATIVE.  
  
 addr.addUPhysical  
 [Pouze C++] Obsahuje[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) struktury, pokud `dwKind` = ADDRESS_KIND_UNMANAGED_PHYSICAL.  
  
 addr.addrMethod  
 [Pouze C++] Obsahuje[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) struktury, pokud `dwKind` = ADDRESS_KIND_METHOD.  
  
 addr.addrField  
 [Pouze C++] Obsahuje[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) struktury, pokud `dwKind` = ADDRESS_KIND_FIELD.  
  
 addr.addrLocal  
 [Pouze C++] Obsahuje[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) struktury, pokud `dwKind` = ADDRESS_KIND_LOCAL.  
  
 addr.addrParam  
 [Pouze C++] Obsahuje[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) struktury, pokud `dwKind` = ADDRESS_KIND_PARAM.  
  
 addr.addrArrayElem  
 [Pouze C++] Obsahuje[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) struktury, pokud `dwKind` = ADDRESS_KIND_ARRAYELEM.  
  
 addr.addrRetVal  
 [Pouze C++] Obsahuje[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) struktury, pokud `dwKind` = ADDRESS_KIND_RETVAL.  
  
 addr.unused  
 Odsazení [C++ pouze].  
  
 Addr  
 [Pouze C++] Název sjednocení.  
  
 unionmember  
 [C# pouze] Tato hodnota musí být zařazena odpovídající struktura typu na základě `dwKind`. V části poznámky pro přidružení mezi `dwKind` a výklad sjednocení.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je součástí [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktury a představuje jeden z několika různých druhů adresy ( `DEBUG_ADDRESS` struktura vyplní volání [getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda).  
  
 [C# pouze] Následující tabulka ukazuje, jak interpretovat `unionmember` člena pro jednotlivé typy adresy. Příklad ukazuje, jak to provést pro jeden typ adresy.  
  
|`dwKind`|`unionmember` interpretovat jako|  
|--------------|----------------------------------|  
|`ADDRESS_KIND_NATIVE`|[NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)|  
|`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`|[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)|  
|`ADDRESS_KIND_UNMANAGED_PHYSICAL`|[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)|  
|`ADDRESS_KIND_METHOD`|[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)|  
|`ADDRESS_KIND_FIELD`|[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)|  
|`ADDRESS_KIND_LOCAL`|[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)|  
|`ADDRESS_KIND_PARAM`|[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)|  
|`ADDRESS_KIND_ARRAYELEM`|[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)|  
|`ADDRESS_KIND_RETVAL`|[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)|  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak interpretovat jednoho druhu adresy (`METADATA_ADDRESS_ARRAYELEM`) z `DEBUG_ADDRESS_UNION` struktury v jazyku C#. Zbývající elementy jde interpretovat stejným způsobem.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(DEBUG_ADDRESS_UNION dau)  
        {  
            if (dau.dwKind == (uint)enum_ADDRESS_KIND.ADDRESS_KIND_METADATA_ARRAYELEM)  
            {  
                 METADATA_ADDRESS_ARRAYELEM arrayElem =  
                     (METADATA_ADDRESS_ARRAYELEM)Marshal.PtrToStructure(dau.unionmember,  
                                 typeof(METADATA_ADDRESS_ARRAYELEM));  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)   
 [Getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)