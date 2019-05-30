---
title: DEBUG_REFERENCE_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_REFERENCE_INFO
helpviewer_keywords:
- DEBUG_REFERENCE_INFO structure
ms.assetid: 24b83d00-d756-42a1-8083-730f998761dc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c22ab1a7d0cb03f66455f76c1d9878a9df76604e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346132"
---
# <a name="debugreferenceinfo"></a>DEBUG_REFERENCE_INFO
Popisuje odkaz.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagDEBUG_REFERENCE_INFO {
    DEBUGREF_INFO_FLAGS dwFields;
    BSTR                bstrName;
    BSTR                bstrType;
    BSTR                bstrValue;
    DBG_ATTRIB_FLAGS    dwAttrib;
    REFERENCE_TYPE.     dwRefType;
    IDebugReference2*   m_pReference;
} DEBUG_REFERENCE_INFO;
```

```csharp
public struct DEBUG_REFERENCE_INFO {
    public uint             dwFields;
    public string           bstrName;
    public string           bstrType;
    public string           bstrValue;
    public ulong            dwAttrib;
    public uint.            dwRefType;
    public IDebugReference2 m_pReference;
};
```

## <a name="members"></a>Členové
`dwFields`\
Kombinace příznaků z [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) výčet, který určuje, která pole jsou vyplněna.

`bstrName`\
Uživatelem zadaný název [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu.

`bstrType`\
Typ odkazu jako formátovaný řetězec.

`bstrValue`\
Hodnota odkazu jako formátovaný řetězec

`dwAttrib`\
Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet, který určuje příznaky pro atributy vlastnosti ladění.

`dwRefType`\
Hodnota z [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md) výčet, který určuje, zda je typ odkazu velký nebo malý.

`m_pReference`\
[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, který určuje referenční informace.

## <a name="remarks"></a>Poznámky
Tato struktura je předána volání [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) metoda být vyplněna. Tato struktura je také vrácen jako část seznamu z [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md) rozhraní, které je pak vrácen z volání [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)
- [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)
- [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md)
- [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
