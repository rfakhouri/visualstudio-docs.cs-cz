---
title: DEBUGREF_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1adab87ed09ca2ff16d837da084d8cc0b76956fe
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318357"
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

## <a name="fields"></a>Pole
`DEBUGREF_INFO_NAME`\
Inicializace/použít `bstrName` pole ve struktuře.

`DEBUGREF_INFO_TYPE`\
Inicializace/použít `bstrType` pole ve struktuře.

`DEBUGREF_INFO_VALUE`\
Inicializace/použít `bstrValue` pole ve struktuře.

`DEBUGREF_INFO_ATTRIB`\
Inicializace/použít `dwAttrib` pole ve struktuře.

`DEBUGREF_INFO_REFTYPE`\
Inicializace/použít `dwRefType` pole ve struktuře.

`DEBUGREF_INFO_REF`\
Inicializace/použít `pReference` pole ve struktuře.

`DEBUGREF_INFO_VALUE_AUTOEXPAND`\
V poli hodnota by měla obsahovat hodnotu rozšířit automaticky, pokud je k dispozici pro tento typ objektu.

`DEBUGREF_INFO_NONE`\
Určuje, jestli jsou nastavené žádné příznaky.

`DEBUGREF_INFO_ALL`\
Označuje masku příznaky.

## <a name="remarks"></a>Poznámky
Tyto příznaky jsou předány [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) a [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) metody označíte, která pole [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury mají být inicializovány.

Používá pro `dwFields` člena `DEBUG_REFERENCE_INFO` struktury k označení pole, která se používá a je platný vrátila strukturu.

Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)
- [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)
