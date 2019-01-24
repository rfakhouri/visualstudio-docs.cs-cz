---
title: PROCESS_INFO_FLAGS | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
ms.assetid: 696951ce-701a-40c2-ac8c-b897f3aae6e2
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 88ff2a1da1f937fd4011932979bd95057eb40dfd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786447"
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Popisuje nebo určuje vlastnosti procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 PIFLAG_SYSTEM_PROCESS  
 Označuje, že proces je systémový proces.  
  
 PIFLAG_DEBUGGER_ATTACHED  
 Označuje, že proces je laděn ladicím programem. Může se jednat [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ladicího programu, nebo mohou být některé další ladicího programu, například WinDbg.  
  
 PIFLAG_PROCESS_STOPPED  
 Označuje, že proces se ukončí. Platí, pouze pokud `PIFLAG_DEBUGGER_ATTACHED` taky. K dispozici v [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] a novější.  
  
 PIFLAG_PROCESS_RUNNING  
 Označuje, že je proces spuštěn. Platí, pouze pokud `PIFLAG_DEBUGGER_ATTACHED` taky. K dispozici v [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] a novější.  
  
## <a name="remarks"></a>Poznámky  
 Používá pro `Flags` člena [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.  
  
 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)
