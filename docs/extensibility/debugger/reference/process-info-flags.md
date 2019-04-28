---
title: PROCESS_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 42a596eb8d720a273d89586427232dcf833f8595
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62864979"
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

Popisuje nebo určuje vlastnosti procesu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
typedef DWORD PROCESS_INFO_FLAGS;
```

```csharp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
```

## <a name="members"></a>Členové

PIFLAG_SYSTEM_PROCESS znamená, že proces systémový proces.

PIFLAG_DEBUGGER_ATTACHED označuje, že proces je laděn ladicím programem. Může se jednat [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladicího programu, nebo mohou být některé další ladicího programu, například WinDbg.

PIFLAG_PROCESS_STOPPED označuje, které proces se ukončí. Platí, pouze pokud `PIFLAG_DEBUGGER_ATTACHED` taky. K dispozici v sadě Visual Studio 2005 a novějších.

PIFLAG_PROCESS_RUNNING označuje, že proces běží. Platí, pouze pokud `PIFLAG_DEBUGGER_ATTACHED` taky. K dispozici v sadě Visual Studio 2005 a novějších.

## <a name="remarks"></a>Poznámky

Používá pro `Flags` člena [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.

Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky

Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také

- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)