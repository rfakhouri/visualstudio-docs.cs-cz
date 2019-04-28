---
title: FIELD_MODIFIERS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_MODIFIERS
helpviewer_keywords:
- FIELD_MODIFIERS enumeration
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b22559af26a0a5f6c8af68726a5ba336e1bcfb4a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924371"
---
# <a name="fieldmodifiers"></a>FIELD_MODIFIERS
Určuje modifikátory pro typ pole.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_FIELD_MODIFIERS {
    FIELD_MOD_NONE             = 0x00000000,

    // Modifier of the field
    FIELD_MOD_ACCESS_NONE      = 0x00000001,
    FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,
    FIELD_MOD_ACCESS_PROTECTED = 0x00000004,
    FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,

    // Storage modifier of the field
    FIELD_MOD_NOMODIFIERS      = 0x00000010,
    FIELD_MOD_STATIC           = 0x00000020,
    FIELD_MOD_CONSTANT         = 0x00000040,
    FIELD_MOD_TRANSIENT        = 0x00000080,
    FIELD_MOD_VOLATILE         = 0x00000100,
    FIELD_MOD_ABSTRACT         = 0x00000200,
    FIELD_MOD_NATIVE           = 0x00000400,
    FIELD_MOD_SYNCHRONIZED     = 0x00000800,
    FIELD_MOD_VIRTUAL          = 0x00001000,
    FIELD_MOD_INTERFACE        = 0x00002000,
    FIELD_MOD_FINAL            = 0x00004000,
    FIELD_MOD_SENTINEL         = 0x00008000,
    FIELD_MOD_INNERCLASS       = 0x00010000,
    FIELD_TYPE_OPTIONAL        = 0x00020000,
    FIELD_MOD_BYREF            = 0x00040000,
    FIELD_MOD_HIDDEN           = 0x00080000,
    FIELD_MOD_MARSHALASOBJECT  = 0x00100000,
    FIELD_MOD_SPECIAL_NAME     = 0x00200000,
    FIELD_MOD_HIDEBYSIG        = 0x00400000,

    FIELD_MOD_WRITEONLY        = 0x80000000,
    FIELD_MOD_ACCESS_MASK      = 0x000000ff,
    FIELD_MOD_MASK             = 0xffffff00,
    FIELD_MOD_ALL              = 0x7fffffff
};
typedef DWORD FIELD_MODIFIERS;
```

```csharp
public enum enum_FIELD_MODIFIERS {
    FIELD_MOD_NONE             = 0x00000000,

    // Modifier of the field
    FIELD_MOD_ACCESS_NONE      = 0x00000001,
    FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,
    FIELD_MOD_ACCESS_PROTECTED = 0x00000004,
    FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,

    // Storage modifier of the field
    FIELD_MOD_NOMODIFIERS      = 0x00000010,
    FIELD_MOD_STATIC           = 0x00000020,
    FIELD_MOD_CONSTANT         = 0x00000040,
    FIELD_MOD_TRANSIENT        = 0x00000080,
    FIELD_MOD_VOLATILE         = 0x00000100,
    FIELD_MOD_ABSTRACT         = 0x00000200,
    FIELD_MOD_NATIVE           = 0x00000400,
    FIELD_MOD_SYNCHRONIZED     = 0x00000800,
    FIELD_MOD_VIRTUAL          = 0x00001000,
    FIELD_MOD_INTERFACE        = 0x00002000,
    FIELD_MOD_FINAL            = 0x00004000,
    FIELD_MOD_SENTINEL         = 0x00008000,
    FIELD_MOD_INNERCLASS       = 0x00010000,
    FIELD_TYPE_OPTIONAL        = 0x00020000,
    FIELD_MOD_BYREF            = 0x00040000,
    FIELD_MOD_HIDDEN           = 0x00080000,
    FIELD_MOD_MARSHALASOBJECT  = 0x00100000,
    FIELD_MOD_SPECIAL_NAME     = 0x00200000,
    FIELD_MOD_HIDEBYSIG        = 0x00400000,

    FIELD_MOD_WRITEONLY        = 0x80000000,
    FIELD_MOD_ACCESS_MASK      = 0x000000ff,
    FIELD_MOD_MASK             = 0xffffff00,
    FIELD_MOD_ALL              = 0x7fffffff
};
```

## <a name="members"></a>Členové
FIELD_MOD_ACCESS_TYPE označuje, že pole není přístupný.

FIELD_MOD_ACCESS_PUBLIC znamená, že pole má veřejný přístup.

FIELD_MOD_ACCESS_PROTECTED označuje, že pole chrání přístup.

FIELD_MOD_ACCESS_PRIVATE znamená, že pole má soukromý přístup.

FIELD_MOD_NOMODIFIERS označuje, že pole nemá žádné modifikátory.

FIELD_MOD_STATIC označuje, že pole je statické.

FIELD_MOD_CONSTANT označuje, že je pole konstanta.

FIELD_MOD_TRANSIENT označuje, že pole je přechodná.

FIELD_MOD_VOLATILE označuje, že pole je typu volatile.

FIELD_MOD_ABSTRACT označuje, že pole je abstraktní.

FIELD_MOD_NATIVE označuje, že pole je nativní.

FIELD_MOD_SYNCHRONIZED označuje, že pole se synchronizuje.

FIELD_MOD_VIRTUAL označuje, že je virtuální pole.

FIELD_MOD_INTERFACE označuje, že pole je rozhraní.

FIELD_MOD_FINAL označuje, že pole je finální.

FIELD_MOD_SENTINEL označuje, že je pole sentinel.

FIELD_MOD_INNERCLASS označuje, že pole je vnitřní třídu.

FIELD_TYPE_OPTIONAL označuje, že pole je volitelné.

FIELD_MOD_BYREF označuje, že pole je argumentem reference. Toto je speciálně pro argumenty metody.

FIELD_MOD_HIDDEN označuje, že pole musí být skrytá nebo zobrazí v jiném kontextu; například [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] statické lokální proměnné.

FIELD_MOD_MARSHALASOBJECT označuje, že pole představuje objekt s `IUnknown` rozhraní.

FIELD_MOD_SPECIAL_NAME znamená, že pole má speciální název, například `.ctor` pro konstruktor ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] pouze).

FIELD_MOD_HIDEBYSIG znamená, že pole má `Overloads` použít klíčové slovo ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] pouze).

FIELD_MOD_WRITEONLY označuje, že pole je jen pro zápis. Tato hodnota není součástí `FIELD_MOD_ALL`, jak je pouze použití pole jen pro zápis pro vyhodnocení funkce. Uživatel musí explicitně požádat o `FIELD_MOD_WRITEONLY` pole.

FIELD_MOD_ACCESS_MASK označuje s maskou pro přístup k poli.

FIELD_MOD_MASK označuje masku modifikátory pole.

## <a name="remarks"></a>Poznámky
Používá pro `dwModifiers` člena [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) struktury.

Tyto hodnoty jsou předány také [enumfields –](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md) metodou filtrování pro konkrétní pole.

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)
- [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)
