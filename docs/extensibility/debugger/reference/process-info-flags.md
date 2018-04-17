---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 91e4c4648108cdc6afa28f5a5dd8f9bfd46fcf59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

Popisuje, nebo určuje vlastnosti procesu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
typedef DWORD PROCESS_INFO_FLAGS;
```

```csharp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
```

## <a name="members"></a>Členové

PIFLAG_SYSTEM_PROCESS  
Označuje, že proces je systémový proces.

PIFLAG_DEBUGGER_ATTACHED  
Označuje, že je proces laděné podle ladicí program. To může být [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladicí program, nebo může být některé jiné ladicího programu, například WinDbg.

PIFLAG_PROCESS_STOPPED  
Označuje, že je proces se zastavil. Platné jenom v případě `PIFLAG_DEBUGGER_ATTACHED` rovněž je zadán. K dispozici v sadě Visual Studio 2005 nebo novější.

PIFLAG_PROCESS_RUNNING  
Označuje, že je proces spuštěný. Platné jenom v případě `PIFLAG_DEBUGGER_ATTACHED` rovněž je zadán. K dispozici v sadě Visual Studio 2005 nebo novější.

## <a name="remarks"></a>Poznámky

Použít pro `Flags` členem [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.

Tyto příznaky mohou být kombinovány s bitové `OR`.

## <a name="requirements"></a>Požadavky

Záhlaví: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také

[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)