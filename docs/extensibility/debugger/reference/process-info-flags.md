---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e95e9f66b804fed102c0d51aa17a1bfe4f51ca5
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
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