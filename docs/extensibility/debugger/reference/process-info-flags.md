---
title: PROCESS_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e0694d83409a492a1d950a17ac5e2298ba9b8578
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309390"
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

## <a name="fields"></a>Pole

`PIFLAG_SYSTEM_PROCESS`\
Označuje, že proces je systémový proces.

`PIFLAG_DEBUGGER_ATTACHED`\
Označuje, že proces je laděn ladicím programem. Může se jednat [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladicího programu, nebo mohou být některé další ladicího programu, například WinDbg.

`PIFLAG_PROCESS_STOPPED`\
Označuje, že proces se ukončí. Platí, pouze pokud `PIFLAG_DEBUGGER_ATTACHED` taky. K dispozici v sadě Visual Studio 2005 a novějších.

`PIFLAG_PROCESS_RUNNING`\
Označuje, že je proces spuštěn. Platí, pouze pokud `PIFLAG_DEBUGGER_ATTACHED` taky. K dispozici v sadě Visual Studio 2005 a novějších.

## <a name="remarks"></a>Poznámky

Používá pro `Flags` člena [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.

Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky

Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:

- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)