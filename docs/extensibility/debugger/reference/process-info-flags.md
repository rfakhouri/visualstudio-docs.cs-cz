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
ms.assetid: 696951ce-701a-40c2-ac8c-b897f3aae6e2
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9ff1df7e73c8f09934504552f33d7f9ce4c537e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 Označuje, že je proces se zastavil. Platné jenom v případě `PIFLAG_DEBUGGER_ATTACHED` rovněž je zadán. K dispozici v [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)] a novější.  
  
 PIFLAG_PROCESS_RUNNING  
 Označuje, že je proces spuštěný. Platné jenom v případě `PIFLAG_DEBUGGER_ATTACHED` rovněž je zadán. K dispozici v [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)] a novější.  
  
## <a name="remarks"></a>Poznámky  
 Použít pro `Flags` členem [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.  
  
 Tyto příznaky mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)