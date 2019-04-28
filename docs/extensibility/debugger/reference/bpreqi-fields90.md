---
title: BPREQI_FIELDS90 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: be07e034b4059ae7ade40a5a248c01bc4a8237b8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924665"
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
Vytvoří výčet platné hodnoty, které určují, který se má načíst informace o požadavku zarážku. Tento výčet rozšiřuje [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BPREQI_FIELDS90
{
    // VS 8.0 values
    BPREQI90_BPLOCATION                = 0x0001,
    BPREQI90_LANGUAGE                  = 0x0002,
    BPREQI90_PROGRAM                   = 0x0004,
    BPREQI90_PROGRAMNAME               = 0x0008,
    BPREQI90_THREAD                    = 0x0010,
    BPREQI90_THREADNAME                = 0x0020,
    BPREQI90_PASSCOUNT                 = 0x0040,
    BPREQI90_CONDITION                 = 0x0080,
    BPREQI90_FLAGS                     = 0x0100,
    BPREQI90_ALLOLDFIELDS              = 0x01ff,
    BPREQI90_VENDOR                    = 0x0200,
    BPREQI90_CONSTRAINT                = 0x0400,
    BPREQI90_TRACEPOINT                = 0x0800,

    // Values added in VS 9.0
    BPREQI90_MACROTRACEPOINT           = 0x1000,

    BPREQI90_ALLFIELDS                 = 0xffff
};
typedef DWORD BPREQI_FIELDS90;
```

```csharp
public enum enum_BPREQI_FIELDS90
{
    // VS 8.0 values
    BPREQI90_BPLOCATION                = 0x0001,
    BPREQI90_LANGUAGE                  = 0x0002,
    BPREQI90_PROGRAM                   = 0x0004,
    BPREQI90_PROGRAMNAME               = 0x0008,
    BPREQI90_THREAD                    = 0x0010,
    BPREQI90_THREADNAME                = 0x0020,
    BPREQI90_PASSCOUNT                 = 0x0040,
    BPREQI90_CONDITION                 = 0x0080,
    BPREQI90_FLAGS                     = 0x0100,
    BPREQI90_ALLOLDFIELDS              = 0x01ff,
    BPREQI90_VENDOR                    = 0x0200,
    BPREQI90_CONSTRAINT                = 0x0400,
    BPREQI90_TRACEPOINT                = 0x0800,

    // Values added in VS 9.0
    BPREQI90_MACROTRACEPOINT           = 0x1000,

    BPREQI90_ALLFIELDS                 = 0xffff
};
```

#### <a name="parameters"></a>Parametry
Inicializovat BPREQI90_BPLOCATION nebo použití `bpLocation` oblasti (umístění zarážky) [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) nebo [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.

Inicializovat BPREQI90_LANGUAGE nebo použití `guidLanguage` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_PROGRAM nebo použití `pProgram` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_PROGRAMNAME nebo použití `bstrProgramName` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_THREAD nebo použití `pThread` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_THREADNAME nebo použití `bstrThreadName` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_PASSCOUNT nebo použití `bpPassCount` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_CONDITION nebo použití `bpCondition` pole (podmínka zarážky) `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_FLAGS nebo použití `dwFlags` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_ALLOLDFIELDS nebo všechna pole pro použití z `BP_REQUEST_INFO` struktury.

Inicializovat BPREQI90_VENDOR nebo použití `guidVendor` pole `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_CONSTRAINT nebo použití `bstrConstraint` pole `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_TRACEPOINT nebo použití `bstrTracepoint` pole `BP_REQUEST_INFO2` struktury.

Inicializovat BPREQI90_MACROTRACEPOINT nebo použití `bstrMacroTracepoint` pole `BP_REQUEST_INFO2` struktury. BPREQI_ALLFIELDS neobsahuje toto pole.

Určuje BPREQI90_ALLFIELDS všechna pole pro `BP_REQUEST_INFO2` struktury.

## <a name="requirements"></a>Požadavky
Záhlaví: Msdbg90.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
