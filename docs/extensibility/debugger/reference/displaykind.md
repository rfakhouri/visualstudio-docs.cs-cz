---
title: DisplayKind | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- DisplayKind enumeration
ms.assetid: 940968c5-6065-4bda-8ee6-c31597db4d71
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1bbb4af7b4269376d912ba312cfe8aacfef2e4ff
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56692759"
---
# <a name="displaykind"></a>DisplayKind
Vytvoří výčet platné hodnoty, které představují typy informací, které mají trvat, než [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu a zobrazí uživateli.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_DisplayKind
{
    DisplayKind_Value = 0x1,
    DisplayKind_Name = 0x2,
    DisplayKind_Type = 0x3,
};
typedef DWORD DisplayKind;
```

```csharp
public enum enum_DisplayKind
{
    DisplayKind_Value = 0x1,
    DisplayKind_Name = 0x2,
    DisplayKind_Type = 0x3,
};
```

#### <a name="parameters"></a>Parametry
DisplayKind_Value hodnotu pole.

DisplayKind_Name název pole.

DisplayKind_Type typu pole.

## <a name="requirements"></a>Požadavky
Záhlaví: EE.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)
