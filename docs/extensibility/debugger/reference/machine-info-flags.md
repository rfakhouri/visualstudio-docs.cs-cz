---
title: MACHINE_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MACHINE_INFO_FLAGS
helpviewer_keywords:
- MACHINE_INFO_FLAGS enumeration
ms.assetid: 1482095d-9a2e-4ef1-9e14-362c0b85194e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 92ffda1188ced40e5a174a0e033263dd2fa2e5a8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913959"
---
# <a name="machineinfoflags"></a>MACHINE_INFO_FLAGS
Použít k popisu na počítači.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_MACHINE_INFO_FLAGS { 
   MCIFLAG_TERMINAL_SERVICES_AVAILABLE = 0x00000001
};
typedef DWORD MACHINE_INFO_FLAGS;
```

```csharp
public enum enum_MACHINE_INFO_FLAGS { 
   MCIFLAG_TERMINAL_SERVICES_AVAILABLE = 0x00000001
};
```

## <a name="members"></a>Členové
 MCIFLAG_TERMINAL_SERVICES_AVAILABLE označuje, že Terminálové služby jsou k dispozici.

## <a name="remarks"></a>Poznámky
 Použít jako `Flags` člena [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) struktury.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)