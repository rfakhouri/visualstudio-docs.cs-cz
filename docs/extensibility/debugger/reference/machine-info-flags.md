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
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 19fb88886d55e38427599a9385485eed8a1bfc07
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461047"
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

## <a name="fields"></a>Pole
 `MCIFLAG_TERMINAL_SERVICES_AVAILABLE`\
 Určuje, že Terminálové služby jsou k dispozici.

## <a name="remarks"></a>Poznámky
 Použít jako `Flags` člena [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) struktury.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)