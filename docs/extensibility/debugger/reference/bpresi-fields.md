---
title: BPRESI_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fac4c65047c51d1213d8be4352c1b8e6efc35c8e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924796"
---
# <a name="bpresifields"></a>BPRESI_FIELDS
Určuje informace, který se má načíst informace o úspěšného vyřešení zarážku.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
typedef DWORD BPRESI_FIELDS;
```

```csharp
public enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
```

## <a name="members"></a>Členové
BPRESI_BPRESLOCATION inicializace/použít `bpResLocation` oblasti (umístění zarážky řešení) [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktury.

BPRESI_PROGRAM inicializace/použít `pProgram` pole `BP_RESOLUTION_INFO` struktury.

BPRESI_THREAD inicializace/použít `pThread` pole `BP_RESOLUTION_INFO` struktury.

BPRESI_ALLFIELDS určuje všechna pole.

## <a name="remarks"></a>Poznámky
Předány [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) indikace polí s [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktury mají být inicializovány.

Tyto příznaky jsou také použity k označení polí s `BP_RESOLUTION_INFO` struktury jsou používány a platné při vrácení této struktury.

Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
