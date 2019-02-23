---
title: BPERESI_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 488c2b1a96d01e0e7dfa9868d2f7e5111adc4e2d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56699428"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
Určuje informace, které se mají načíst informace o neúspěšných rozlišení zarážku.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
typedef DWORD BPERESI_FIELDS;
```

```csharp
public enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
```

## <a name="members"></a>Členové
PERESI_BPRESLOCATION inicializace/použít `bpResLocation` oblasti (umístění zarážky řešení) [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) struktury.

BPERESI_PROGRAM inicializace/použít `pProgram` pole `BP_ERROR_RESOLUTION_INFO` struktury.

BPERESI_THREAD inicializace/použít `pThread` pole `BP_ERROR_RESOLUTION_INFO` struktury.

BPERESI_MESSAGE inicializace/použít `bstrMessage` pole `BP_ERROR_RESOLUTION_INFO` struktury.

BPERESI_TYPE inicializace/použít `dwType` pole (typ zarážky) `BP_ERROR_RESOLUTION_INFO` struktury.

BPERESI_ALLFIELDS inicializace/použít všechna pole `BP_ERROR_RESOLUTION_INFO` struktury.

## <a name="remarks"></a>Poznámky
Předán jako parametr [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) indikace polí s [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) struktury mají být inicializovány.

Tyto hodnoty jsou také použity k označení, která pole v `BP_ERROR_RESOLUTION_INFO` struktury jsou používány a platné při vrácení této struktury.

Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)
