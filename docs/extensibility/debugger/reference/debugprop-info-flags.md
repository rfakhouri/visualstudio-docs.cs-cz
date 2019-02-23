---
title: DEBUGPROP_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 131e014e3714df708c5ef1526ecb911531c5a5c3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689106"
---
# <a name="debugpropinfoflags"></a>DEBUGPROP_INFO_FLAGS
Určuje, jaké informace se mají načíst informace o objektu vlastnosti ladění.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_DEBUGPROP_INFO_FLAGS {
    DEBUGPROP_INFO_FULLNAME          = 0x00000001,
    DEBUGPROP_INFO_NAME              = 0x00000002,
    DEBUGPROP_INFO_TYPE              = 0x00000004,
    DEBUGPROP_INFO_VALUE             = 0x00000008,
    DEBUGPROP_INFO_ATTRIB            = 0x00000010,
    DEBUGPROP_INFO_PROP              = 0x00000020,
    DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,
    DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,
    DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,
    DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000
    DEBUGPROP_INFO_NONE              = 0x00000000,
    DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |
                                        DEBUGPROP_INFO_NAME |
                                        DEBUGPROP_INFO_TYPE |
                                        DEBUGPROP_INFO_VALUE,
    DEBUGPROP_INFO_ALL               = 0xffffffff
};
typedef DWORD DEBUGPROP_INFO_FLAGS;
```

```csharp
public enum enum_DEBUGPROP_INFO_FLAGS {
    DEBUGPROP_INFO_FULLNAME          = 0x00000001,
    DEBUGPROP_INFO_NAME              = 0x00000002,
    DEBUGPROP_INFO_TYPE              = 0x00000004,
    DEBUGPROP_INFO_VALUE             = 0x00000008,
    DEBUGPROP_INFO_ATTRIB            = 0x00000010,
    DEBUGPROP_INFO_PROP              = 0x00000020,
    DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,
    DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,
    DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,
    DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000
    DEBUGPROP_INFO_NONE              = 0x00000000,
    DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |
                                        DEBUGPROP_INFO_NAME |
                                        DEBUGPROP_INFO_TYPE |
                                        DEBUGPROP_INFO_VALUE,
    DEBUGPROP_INFO_ALL               = 0xffffffff
};
```

## <a name="members"></a>Členové
DEBUGPROP_INFO_FULLNAME inicializace/použít `bstrFullName` pole.

DEBUGPROP_INFO_NAME inicializace/použít `bstrName` pole.

DEBUGPROP_INFO_TYPE inicializace/použít `bstrType` pole.

DEBUGPROP_INFO_VALUE inicializace/použít `bstrValue` pole.

DEBUGPROP_INFO_ATTRIB inicializace/použít `dwAttrib` pole.

DEBUGPROP_INFO_PROP inicializace/použít `pProperty` pole s údajem o [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní.

DEBUGPROP_INFO_VALUE_AUTOEXPAND Určuje, že hodnota pole by měl obsahovat hodnotu automaticky rozbaleny, pokud je k dispozici pro tento typ objektu.

DEBUGPROP_INFO_VALUE_NOFUNCEVAL zastaralé.

DEBUGPROP_INFO_VALUE_RAW nevrátí žádné beautified hodnoty nebo členy (to znamená, Neformátovat hodnoty).

DEBUGPROP_INFO_VALUE_NO_TOSTRING nevrátí žádné speciální syntetizovaný hodnoty (například Nevolejte `ToString()` na objekt k vytvoření hodnoty).

DEBUGPROP_INFO_NONE Určuje, že jsou nastaveny žádné příznaky.

DEBUGPROP_INFO_STANDARD inicializace/použít `dwAttrib`, `bstrName`, `bstrType`, a `bstrValue` pole.

DEBUGPROP_INFO_All označuje masku všechny příznaky.

## <a name="remarks"></a>Poznámky
Tyto hodnoty jsou předány [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md), [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), a [enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) metody k označení pole, která mají být inicializovány [ DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury.

Tyto hodnoty se používají i pro `dwFields` člena `DEBUG_PROPERTY_INFO` struktury k označení, která pole struktury jsou používány a platný, pokud vrátí strukturu.

Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)
- [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)
- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
