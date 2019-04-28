---
title: FIELD_KIND | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_KIND
helpviewer_keywords:
- FIELD_KIND enumeration
ms.assetid: fd522b9c-52e2-42fa-939d-343347d5c3b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 46b965def820771b0bab883c1bdd9bf90d18414e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924429"
---
# <a name="fieldkind"></a>FIELD_KIND
Určuje typ pole, které jsou součástí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_FIELD_KIND {
    FIELD_KIND_NONE       = 0x00000000,

    // Type of field
    FIELD_KIND_TYPE       = 0x00000001,
    FIELD_KIND_SYMBOL     = 0x00000002,

    // Storage type of the field
    FIELD_TYPE_PRIMITIVE  = 0x00000010,
    FIELD_TYPE_STRUCT     = 0x00000020,
    FIELD_TYPE_CLASS      = 0x00000040,
    FIELD_TYPE_INTERFACE  = 0x00000080,
    FIELD_TYPE_UNION      = 0x00000100,
    FIELD_TYPE_ARRAY      = 0x00000200,
    FIELD_TYPE_METHOD     = 0x00000400,
    FIELD_TYPE_BLOCK      = 0x00000800,
    FIELD_TYPE_POINTER    = 0x00001000,
    FIELD_TYPE_ENUM       = 0x00002000,
    FIELD_TYPE_LABEL      = 0x00004000,
    FIELD_TYPE_TYPEDEF    = 0x00008000,
    FIELD_TYPE_BITFIELD   = 0x00010000,
    FIELD_TYPE_NAMESPACE  = 0x00020000,
    FIELD_TYPE_MODULE     = 0x00040000,
    FIELD_TYPE_DYNAMIC    = 0x00080000,
    FIELD_TYPE_PROP       = 0x00100000,
    FIELD_TYPE_INNERCLASS = 0x00200000,
    FIELD_TYPE_REFERENCE  = 0x00400000,
    FIELD_TYPE_EXTENDED   = 0x00800000,

    // Specific information about symbols
    FIELD_SYM_MEMBER      = 0x01000000,
    FIELD_SYM_LOCAL       = 0x02000000,
    FIELD_SYM_PARAM       = 0x04000000,
    FIELD_SYM_THIS        = 0x08000000,
    FIELD_SYM_GLOBAL      = 0x10000000,
    FIELD_SYM_PROP_GETTER = 0x20000000,
    FIELD_SYM_PROP_SETTER = 0x40000000,
    FIELD_SYM_EXTENDED    = 0x80000000,

    FIELD_KIND_MASK       = 0x0000000f,
    FIELD_TYPE_MASK       = 0x00fffff0,
    FIELD_SYM_MASK        = 0xff000000,

    FIELD_KIND_ALL        = 0xffffffff
};
typedef DWORD FIELD_KIND;
```

```csharp
public enum enum_FIELD_KIND {
    FIELD_KIND_NONE       = 0x00000000,

    // Type of field
    FIELD_KIND_TYPE       = 0x00000001,
    FIELD_KIND_SYMBOL     = 0x00000002,

    // Storage type of the field
    FIELD_TYPE_PRIMITIVE  = 0x00000010,
    FIELD_TYPE_STRUCT     = 0x00000020,
    FIELD_TYPE_CLASS      = 0x00000040,
    FIELD_TYPE_INTERFACE  = 0x00000080,
    FIELD_TYPE_UNION      = 0x00000100,
    FIELD_TYPE_ARRAY      = 0x00000200,
    FIELD_TYPE_METHOD     = 0x00000400,
    FIELD_TYPE_BLOCK      = 0x00000800,
    FIELD_TYPE_POINTER    = 0x00001000,
    FIELD_TYPE_ENUM       = 0x00002000,
    FIELD_TYPE_LABEL      = 0x00004000,
    FIELD_TYPE_TYPEDEF    = 0x00008000,
    FIELD_TYPE_BITFIELD   = 0x00010000,
    FIELD_TYPE_NAMESPACE  = 0x00020000,
    FIELD_TYPE_MODULE     = 0x00040000,
    FIELD_TYPE_DYNAMIC    = 0x00080000,
    FIELD_TYPE_PROP       = 0x00100000,
    FIELD_TYPE_INNERCLASS = 0x00200000,
    FIELD_TYPE_REFERENCE  = 0x00400000,
    FIELD_TYPE_EXTENDED   = 0x00800000,

    // Specific information about symbols
    FIELD_SYM_MEMBER      = 0x01000000,
    FIELD_SYM_LOCAL       = 0x02000000,
    FIELD_SYM_PARAM       = 0x04000000,
    FIELD_SYM_THIS        = 0x08000000,
    FIELD_SYM_GLOBAL      = 0x10000000,
    FIELD_SYM_PROP_GETTER = 0x20000000,
    FIELD_SYM_PROP_SETTER = 0x40000000,
    FIELD_SYM_EXTENDED    = 0x80000000,

    FIELD_KIND_MASK       = 0x0000000f,
    FIELD_TYPE_MASK       = 0x00fffff0,
    FIELD_SYM_MASK        = 0xff000000,

    FIELD_KIND_ALL        = 0xffffffff
};
```

## <a name="members"></a>Členové
FIELD_KIND_TYPE označuje, že pole je typu pouze.

FIELD_KIND_SYMBOL označuje, že pole je symbol, typ, název a další informace.

FIELD_TYPE_PRIMITIVE znamená, že pole primitivních datových typů.

FIELD_TYPE_STRUCT označuje, že pole je struktura.

FIELD_TYPE_CLASS označuje, že pole je třída.

FIELD_TYPE_INTERFACE označuje, že pole je rozhraní.

FIELD_TYPE_UNION označuje, že pole je sjednocení.

FIELD_TYPE_ARRAY označuje, že pole je pole.

FIELD_TYPE_METHOD označuje, že pole je metoda.

FIELD_TYPE_BLOCK označuje, že pole je blok.

FIELD_TYPE_POINTER označuje, že pole je ukazatel.

FIELD_TYPE_ENUM označuje, že pole je výčtový datový typ.

FIELD_TYPE_LABEL označuje, že pole je popisek.

FIELD_TYPE_TYPEDEF označuje, že pole je definice typu.

FIELD_TYPE_BITFIELD označuje, že pole je bitového pole.

FIELD_TYPE_NAMESPACE označuje, že pole je obor názvů.

FIELD_TYPE_MODULE označuje, že pole je modul.

FIELD_TYPE_DYNAMIC označuje, že pole je dynamická.

FIELD_TYPE_PROP označuje, že pole je vlastnost.

FIELD_TYPE_INNERCLASS označuje, že pole je vnitřní třídu.

FIELD_TYPE_REFERENCE označuje, že pole je odkaz.

FIELD_TYPE_EXTENDED vyhrazen pro budoucí použití.

FIELD_SYM_MEMBER označuje, že pole je členem.

FIELD_SYM_LOCAL označuje, že pole je místní.

FIELD_SYM_PARAMETER označuje, že pole je parametr.

FIELD_SYM_THIS označuje, že pole je ukazatel "Tento".

FIELD_SYM_GLOBAL označuje, že pole je globální.

FIELD_SYM_PROP_GETTER označuje, že pole načte vlastnosti.

FIELD_SYM_PROP_SETTER označuje, že pole nastaví vlastnosti.

FIELD_SYM_EXTENDED vyhrazen pro budoucí použití.

FIELD_KIND_MASK označuje maska pro typy polí.

FIELD_TYPE_MASK označuje maska pro typy polí.

FIELD_SYM_MASK označuje maska informací o symbolu.

## <a name="remarks"></a>Poznámky
Vrácená z volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metody.

V závislosti na typu pole [QueryInterface](/cpp/atl/queryinterface) lze volat pro [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní pro konkrétnější formu rozhraní. Například pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí `FIELD_TYPE_METHOD`, pak můžete volat `QueryInterface` na můžu`DebugField` získat [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) rozhraní.

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)
- [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
