---
title: Třída TaskScheduler – vnitřní členy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 427a84b3dcda0471f5ec9d71883a5a8e859bb92d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176703"
---
# <a name="taskscheduler-class---internal-members"></a>Třída TaskScheduler – vnitřní členy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Toto téma popisuje interní členy <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třída, která vám pomůže implementovat vlastní ladicího programu. Obecné informace o této třídy, najdete v článku <xref:System.Threading.Tasks.TaskScheduler> téma referenčních informací.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## <a name="members"></a>Členové  
  
### <a name="methods"></a>Metody  
  
|Name|Popis|  
|----------|-----------------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Načte pole všech naplánovaných úloh.|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
