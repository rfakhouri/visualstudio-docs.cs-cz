---
title: DEBUG_PROPERTY_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_PROPERTY_INFO
helpviewer_keywords:
- DEBUG_PROPERTY_INFO structure
ms.assetid: 5a085d18-62c6-4740-b9e9-3f5db6bfdf7f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7804cfad48d5029e16619b5ae524fa6e761f11b4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346171"
---
# <a name="debugpropertyinfo"></a>DEBUG_PROPERTY_INFO
Obsahuje informace o vlastnosti ladění.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagDEBUG_PROPERTY_INFO {
    DEBUGPROP_INFO_FLAGS dwValidFields;
    BSTR                 bstrFullName;
    BSTR                 bstrName;
    BSTR                 bstrType;
    BSTR                 bstrValue;
    IDebugProperty2*     pProperty;
    DBG_ATTRIB_FLAGS     dwAttrib;
} DEBUG_PROPERTY_INFO;
```

```csharp
public struct DEBUG_PROPERTY_INFO {
    public uint            dwValidFields;
    public string          bstrFullName;
    public string          bstrName;
    public string          bstrType;
    public string          bstrValue;
    public IDebugProperty2 pProperty;
    public ulong           dwAttrib;
};
```

## <a name="members"></a>Členové
`dwValidFields`\
Kombinace příznaků z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje, která pole jsou vyplněna.

`bstrFullName`\
Celý název vlastnosti.

`bstrName`\
Název vlastnosti v rámci kontextu.

`bstrType`\
Typ vlastnosti jako formátovaný řetězec.

`bstrValue`\
Hodnota vlastnosti jako formátovaný řetězec.

`pProperty`\
[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objektem popsaným touto strukturou.

`dwAttrib`\
Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet popisující vlastnosti této vlastnosti.

## <a name="remarks"></a>Poznámky
Vlastnost je objekt hierarchickou povahu, který má název, typ a hodnotu. Například vlastnost popsat lokální proměnné, parametry, sledovat proměnné a výrazy a registry.

Tato struktura je předán [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metody, kde je vyplněna. Tato struktura je také vrácen jako část seznamu z této struktury [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) rozhraní, které je pak vrácen z volání [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) a [ Enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)
- [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)
- [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)
- [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)
