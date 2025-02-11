---
title: BPREQI_FIELDS90 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3f4d6df181ac15746202ae9f67e7b8874848e8f3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350549"
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

## <a name="fields"></a>Pole
`BPREQI90_BPLOCATION`\
Inicializace nebo použijte `bpLocation` oblasti (umístění zarážky) [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) nebo [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.

`BPREQI90_LANGUAGE`\
Inicializace nebo použijte `guidLanguage` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_PROGRAM`\
Inicializace nebo použijte `pProgram` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_PROGRAMNAME`\
Inicializace nebo použijte `bstrProgramName` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_THREAD`\
Inicializace nebo použijte `pThread` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_THREADNAME`\
Inicializace nebo použijte `bstrThreadName` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_PASSCOUNT`\
Inicializace nebo použijte `bpPassCount` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_CONDITION`\
Inicializace nebo použijte `bpCondition` pole (podmínka zarážky) `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_FLAGS`\
Inicializace nebo použijte `dwFlags` pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.

`BPREQI90_ALLOLDFIELDS`\
Inicializovat nebo použít pro všechna pole aplikace `BP_REQUEST_INFO` struktura.

`BPREQI90_VENDOR`\
Inicializace nebo použijte `guidVendor` pole `BP_REQUEST_INFO2` struktury.

`BPREQI90_CONSTRAINT`\
Inicializace nebo použijte `bstrConstraint` pole `BP_REQUEST_INFO2` struktury.

`BPREQI90_TRACEPOINT`\
Inicializace nebo použijte `bstrTracepoint` pole `BP_REQUEST_INFO2` struktury.

`BPREQI90_MACROTRACEPOINT`\
Inicializace nebo použijte `bstrMacroTracepoint` pole `BP_REQUEST_INFO2` struktury. BPREQI_ALLFIELDS neobsahuje toto pole.

`BPREQI90_ALLFIELDS`\
Určuje všechna pole `BP_REQUEST_INFO2` struktury.

## <a name="requirements"></a>Požadavky
Záhlaví: Msdbg90.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
