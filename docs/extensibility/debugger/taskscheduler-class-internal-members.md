---
title: Třída TaskScheduler – vnitřní členy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 18cd3ec809df921d6baefbf8018fefc77db238d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="taskscheduler-class---internal-members"></a>Třída TaskScheduler – vnitřní členy
Toto téma popisuje vnitřní členy <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třídu, která vám pomůže implementovat vlastní ladicí program. Obecné informace o této třídy, najdete v článku <xref:System.Threading.Tasks.TaskScheduler> referenční téma.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## <a name="members"></a>Členové  
  
### <a name="methods"></a>Metody  
  
|Název|Popis|  
|----------|-----------------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Načte pole všechny naplánované úlohy.|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Načte pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)