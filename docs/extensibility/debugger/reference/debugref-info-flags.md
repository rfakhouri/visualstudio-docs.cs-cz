---
title: DEBUGREF_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 50efecb332be0a1cd9d9ff2c92dc97d5096eb44e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686289"
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
Určuje, jaké informace se mají načíst informace o ladění referenční objekt.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_DEBUGREF_INFO_FLAGS {
    DEBUGREF_INFO_NAME             = 0x00000001,
    DEBUGREF_INFO_TYPE             = 0x00000002,
    DEBUGREF_INFO_VALUE            = 0x00000004,
    DEBUGREF_INFO_ATTRIB           = 0x00000008,
    DEBUGREF_INFO_REFTYPE          = 0x00000010,
    DEBUGREF_INFO_REF              = 0x00000020,
    DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,
    DEBUGREF_INFO_NONE             = 0x00000000,
    DEBUGREF_INFO_ALL              = 0xffffffff
};
typedef DWORD DEBUGREF_INFO_FLAGS;
```

```csharp
public enum enum_DEBUGREF_INFO_FLAGS {
    DEBUGREF_INFO_NAME             = 0x00000001,
    DEBUGREF_INFO_TYPE             = 0x00000002,
    DEBUGREF_INFO_VALUE            = 0x00000004,
    DEBUGREF_INFO_ATTRIB           = 0x00000008,
    DEBUGREF_INFO_REFTYPE          = 0x00000010,
    DEBUGREF_INFO_REF              = 0x00000020,
    DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,
    DEBUGREF_INFO_NONE             = 0x00000000,
    DEBUGREF_INFO_ALL              = 0xffffffff
};
```

## <a name="members"></a>Členové
DEBUGREF_INFO_NAME inicializace/použít `bstrName` pole ve struktuře.

DEBUGREF_INFO_TYPE inicializace/použít `bstrType` pole ve struktuře.

DEBUGREF_INFO_VALUE inicializace/použít `bstrValue` pole ve struktuře.

DEBUGREF_INFO_ATTRIB inicializace/použít `dwAttrib` pole ve struktuře.

DEBUGREF_INFO_REFTYPE inicializace/použít `dwRefType` pole ve struktuře.

DEBUGREF_INFO_REF inicializace/použít `pReference` pole ve struktuře.

DEBUGREF_INFO_VALUE_AUTOEXPAND pole hodnota by měla obsahovat hodnotu rozšířit automaticky, pokud je k dispozici pro tento typ objektu.

DEBUGREF_INFO_NONE znamená, že jsou nastaveny žádné příznaky.

DEBUGREF_INFO_ALL označuje maska příznaků.

## <a name="remarks"></a>Poznámky
Tyto příznaky jsou předány [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) a [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) metody označíte, která pole [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury mají být inicializovány.

Používá pro `dwFields` člena `DEBUG_REFERENCE_INFO` struktury k označení pole, která se používá a je platný vrátila strukturu.

Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)
- [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)
