---
title: DEBUG_ADDRESS_UNION | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_ADDRESS_UNION
helpviewer_keywords:
- DEBUG_ADDRESS_UNION union
ms.assetid: e3d11aab-de0d-4109-b5dc-11e07e64382d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3dbd114fb06bfd688c720744dbbad69bd0dae6aa
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346286"
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

## <a name="members"></a>Členové
`dwKind`\
Hodnota z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet určující způsob interpretace sjednocení.

`addr.addrNative`\
[C++ pouze] Obsahuje [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) strukturu Pokud `dwKind` = ADDRESS_KIND_NATIVE.

`addr.addrThisRel`\
[C++ pouze] Obsahuje[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) strukturu Pokud `dwKind` = ADDRESS_KIND_UNMANAGED_THIS_RELATIVE.

`addr.addUPhysical`\
[C++ pouze] Obsahuje[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) strukturu Pokud `dwKind` = ADDRESS_KIND_UNMANAGED_PHYSICAL.

`addr.addrMethod`\
[C++ pouze] Obsahuje[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) strukturu Pokud `dwKind` = ADDRESS_KIND_METHOD.

`addr.addrField`\
[C++ pouze] Obsahuje[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) strukturu Pokud `dwKind` = ADDRESS_KIND_FIELD.

`addr.addrLocal`\
[C++ pouze] Obsahuje[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) strukturu Pokud `dwKind` = ADDRESS_KIND_LOCAL.

`addr.addrParam`\
[C++ pouze] Obsahuje[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) strukturu Pokud `dwKind` = ADDRESS_KIND_PARAM.

`addr.addrArrayElem`\
[C++ pouze] Obsahuje[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) strukturu Pokud `dwKind` = ADDRESS_KIND_ARRAYELEM.

`addr.addrRetVal`\
[C++ pouze] Obsahuje[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) strukturu Pokud `dwKind` = ADDRESS_KIND_RETVAL.

`addr.unused`\
[C++ pouze] odsazení.

`addr`\
[C++ pouze] Název sjednocení.

`unionmember`\
[C# pouze] Tato hodnota musí být zařazen do struktury odpovídající typu na základě `dwKind`. Viz poznámky pro přidružení mezi `dwKind` a interpretaci sjednocení.

## <a name="remarks"></a>Poznámky
Tato struktura je součástí [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktury a představuje jeden z několika různých druhů adresy ( `DEBUG_ADDRESS` struktura je vyplněna voláním [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda).

 [C# pouze] Následující tabulka ukazuje, jak interpretovat `unionmember` člen pro každý druh adresu. Příklad ukazuje, jak to lze provést pro jeden typ adresy.

|`dwKind`|`unionmember` interpretováno jako|
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
Tento příklad ukazuje, jak interpretovat jeden typ adresy (`METADATA_ADDRESS_ARRAYELEM`) z `DEBUG_ADDRESS_UNION` struktura v jazyce C#. Stejným způsobem, může být interpretován zbývající prvky.

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

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
- [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
- [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)
