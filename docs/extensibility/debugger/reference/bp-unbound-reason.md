---
title: BP_UNBOUND_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 65393f6e162cb15ded7a0e598e360c7ce90bb3cd
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717660"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
Poskytuje z důvodů, proč nevázaná zarážku.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_UNBOUND_REASON {
    BPUR_UNKNOWN           = 0x0000,
    BPUR_CODE_UNLOADED     = 0x0002,
    BPUR_BREAKPOINT_REBIND = 0x0003,
    BPUR_BREAKPOINT_ERROR  = 0x0004
};
typedef DWORD BP_UNBOUND_REASON;
```

```csharp
public enum enum_BP_UNBOUND_REASON {
    BPUR_UNKNOWN           = 0x0000,
    BPUR_CODE_UNLOADED     = 0x0002,
    BPUR_BREAKPOINT_REBIND = 0x0003,
    BPUR_BREAKPOINT_ERROR  = 0x0004
};
```

## <a name="members"></a>Členové
BPUR_UNKNOWN důvod není znám.

BPUR_CODE_UNLOADED kód, který obsahuje zarážku byl uvolněn.

BPUR_BREAKPOINT_REBIND zarážku bylo znovu připojeno, do jiného umístění. To může dojít po úpravě a pokračovat v operacích přesun zarážku nebo zarážku je vázán na soubor s cestou, která již není platný.

Potom, co je svázána se omylem vyhodnotí BPUR_ BREAKPOINT_ERROR zarážku. K tomu dochází na spravovaných zarážky, jejíž podmínky už nejsou platné.

## <a name="remarks"></a>Poznámky
Vrácené [getreason –](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)
