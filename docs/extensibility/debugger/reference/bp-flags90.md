---
title: BP_FLAGS90 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5c423b8ecf0e4591913be5ef875057a947f42614
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66319159"
---
# <a name="bpflags90"></a>BP_FLAGS90
Vytvoří výčet platných hodnot pro volitelné příznaky. Volitelné příznaky slouží k určení dalších informací při nastavení zarážky. Tento výčet rozšiřuje [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_FLAGS90
{
    // VS 8.0 values
    BP90_FLAG_NONE               = 0x0000,
    BP90_FLAG_MAP_DOCPOSITION    = 0x0001,
    BP90_FLAG_DONT_STOP          = 0x0002,

    // Values added in VS 9.0
    BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,
};
typedef DWORD BP_FLAGS90;
```

```csharp
public enum enum_BP_FLAGS90
{
    // VS 8.0 values
    BP90_FLAG_NONE                = 0x0000,
    BP90_FLAG_MAP_DOCPOSITION     = 0x0001,
    BP90_FLAG_DONT_STOP           = 0x0002,

    // Values added in VS 9.0
    BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,
};
```

## <a name="fields"></a>Pole
`BP90_FLAG_NONE`\
Určuje příznak bez zarážek.

`BP90_FLAG_MAP_DOCPOSITION`\
Určuje, že ladicí stroj (DE) by měl mapovat zarážky pomocí pozice dokumentu. To se vztahuje pouze na zarážky nastavené v skript orientovaného zdrojových souborech, jako je například stránek ASP (Active Server).

`BP90_FLAG_DONT_STOP`\
Určuje, že zarážka by měla být zpracovány ladicího stroje, ale, že ladicí stroj nakonec by neměl zastavit To znamená [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) nesmí být rozesílaná objektu události. Tento příznak slouží k používá hlavně s body trasování.

`BP90_FLAG_TRACEPOINT_CONTINUE`\
Použít nativní ladicí modul k určení, zda krokování stavu by měla zůstat nezaškrtnutá. Se liší od BP90_FLAG_DONT_STOP protože BP90_FLAG_DONT_STOP není nastavená, pokud bod trasování provede makro.

## <a name="requirements"></a>Požadavky
Záhlaví: Msdbg90.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
