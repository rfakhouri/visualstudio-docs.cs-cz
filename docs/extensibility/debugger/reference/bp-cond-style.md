---
title: BP_COND_STYLE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 70ab3655d27e810b3c05d0e0e81d81bc15a26950
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925205"
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
Určuje styl podmínku zarážky pro čekající a vázán zarážky.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
typedef DWORD BP_COND_STYLE;
```

```csharp
public enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
```

## <a name="members"></a>Členové
Zarážka BP_COND_NONE aktivuje se při dosažení zarážky na pozici. Není zadaná žádná podmínka zarážky.

BP_COND_WHEN_TRUE aktivuje zarážku, jen když podmíněný výraz přidružený k zarážce vyhodnocen `true`.

Je aktivována BP_COND_WHEN_CHANGED zarážky pouze v případě, že hodnota podmíněný výraz přidružený k zarážce byl změněn z jeho předchozího vyhodnocení.

## <a name="remarks"></a>Poznámky
Používá pro `styleCondition` člena [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) struktury.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
