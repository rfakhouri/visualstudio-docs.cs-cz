---
title: FIELD_INFO_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- FIELD_INFO_FIELDS
helpviewer_keywords:
- FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cab1d06c868f0236d1d24c186af705e9adab717e
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317468"
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
Určuje, jaké informace o načtení [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_FIELD_INFO_FIELDS { 
    FIF_FULLNAME  = 0x0001,
    FIF_NAME      = 0x0002,
    FIF_TYPE      = 0x0004,
    FIF_MODIFIERS = 0x0008,
    FIF_ALL       = 0xffffffff,
    FIF_NONE      = 0x0000
};
typedef DWORD FIELD_INFO_FIELDS;
```

```csharp
public enum enum_FIELD_INFO_FIELDS {
    FIF_FULLNAME  = 0x0001,
    FIF_NAME      = 0x0002,
    FIF_TYPE      = 0x0004,
    FIF_MODIFIERS = 0x0008,
    FIF_ALL       = 0xffffffff,
    FIF_NONE      = 0x0000
};
```

## <a name="members"></a>Členové
FIF_FULLNAME  
Inicializace/použít `bstrFullName` pole [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) struktury.

FIF_NAME  
Inicializace/použít `bstrName` pole `FIELD_INFO` struktury.

FIF_TYPE  
Inicializace/použít `bstrType` pole `FIELD_INFO` struktury.

FIF_MODIFIERS  
Inicializace/použít `bstrModifiers` pole `FIELD_INFO` struktury.

## <a name="remarks"></a>Poznámky
Tyto hodnoty jsou také předat jako argument [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) metody určíte, jaké pole [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) struktury mají být inicializovány.

Tyto hodnoty jsou také používány v `dwFields` člena `FIELD_INFO` struktury k označení pole, která se používá a je platný.

Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)  
[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)  
[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)
