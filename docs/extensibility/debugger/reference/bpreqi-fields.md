---
title: BPREQI_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPREQI_FIELDS
helpviewer_keywords:
- BPREQI_FIELDS enumeration
ms.assetid: 679e771e-4a79-484e-af37-f962ef4aa245
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 25b95e2934de9d09ef9541162b05920a04f645bd
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723042"
---
# <a name="bpreqifields"></a>BPREQI_FIELDS
Určuje informace, které se mají načíst informace o požadavku zarážku.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BPREQI_FIELDS {
    BPREQI_BPLOCATION   = 0x0001,
    BPREQI_LANGUAGE     = 0x0002,
    BPREQI_PROGRAM      = 0x0004,
    BPREQI_PROGRAMNAME  = 0x0008,
    BPREQI_THREAD       = 0x0010,
    BPREQI_THREADNAME   = 0x0020,
    BPREQI_PASSCOUNT    = 0x0040,
    BPREQI_CONDITION    = 0x0080,
    BPREQI_FLAGS        = 0x0100,
    BPREQI_ALLOLDFIELDS = 0x01ff
    BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only
    BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only
    BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only
    BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only
};
typedef DWORD BPREQI_FIELDS;
```

```csharp
public enum enum_BPREQI_FIELDS {
    BPREQI_BPLOCATION   = 0x0001,
    BPREQI_LANGUAGE     = 0x0002,
    BPREQI_PROGRAM      = 0x0004,
    BPREQI_PROGRAMNAME  = 0x0008,
    BPREQI_THREAD       = 0x0010,
    BPREQI_THREADNAME   = 0x0020,
    BPREQI_PASSCOUNT    = 0x0040,
    BPREQI_CONDITION    = 0x0080,
    BPREQI_FLAGS        = 0x0100,
    BPREQI_ALLOLDFIELDS = 0x01ff
    BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only
    BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only
    BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only
    BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only
};
```

## <a name="members"></a>Členové
BPREQI_BPLOCATION inicializace/použít `bpLocation` oblasti (umístění zarážky) [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) nebo [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.

BPREQI_LANGUAGE inicializace/použít `guidLanguage` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_PROGRAM inicializace/použít `pProgram` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_PROGRAMNAME inicializace/použít `bstrProgramName` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_THREAD inicializace/použít `pThread` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_THREADNAME inicializace/použít `bstrThreadName` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_PASSCOUNT inicializace/použít `bpPassCount` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_CONDITION inicializace/použít `bpCondition` pole (podmínka zarážky) `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

BPREQI_FLAGS inicializace/použít `dwFlags` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Pole BPREQI_ALLOLDFIELDS inicializace nebo použijte hodnotu all pro aplikace `BP_REQUEST_INFO` struktura.

BPREQI_VENDOR inicializace/použít `guidVendor` pole `BP_REQUEST_INFO2` struktury.

BPREQI_CONSTRAINT inicializace/použít `bstrConstraint` pole `BP_REQUEST_INFO2` struktury.

BPREQI_TRACEPOINT inicializace/použít `bstrTracepoint` pole `BP_REQUEST_INFO2` struktury.

Určuje BPREQI_ALLFIELDS všechna pole pro `BP_REQUEST_INFO2` struktury.

## <a name="remarks"></a>Poznámky
Předán jako argument [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) a [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) metody k určení polí s [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2 ](../../../extensibility/debugger/reference/bp-request-info2.md) struktury mají být inicializovány.

Tyto příznaky jsou také použity k označení polí s `BP_REQUEST_INFO` a `BP_REQUEST_INFO2` struktury jsou používány a platný, pokud každá struktura je vrácen.

Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
