---
title: Task – třída – vnitřní členy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, Task class [.NET Framework]
- Task class [.NET Framework debug engines]
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 161572ece44f3a9f07c9eb40638ca98170e3a86c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="task-class---internal-members"></a>Task – třída – vnitřní členy
Toto téma popisuje vnitřní členy <xref:System.Threading.Tasks.Task?displayProperty=fullName> třídu, která vám pomůže implementovat vlastní ladicí program. Obecné informace o této třídy, najdete v článku <xref:System.Threading.Tasks.Task> referenční téma.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.class public auto ansi System.Threading.Tasks.Task  
       extends System.Object  
       implements System.Threading.IThreadPoolWorkItem,  
                  System.IAsyncResult,  
                  System.IDisposable,  
                  System.Threading.ICancelableOperation  
```  
  
## <a name="members"></a>Členové  
  
### <a name="methods"></a>Metody  
  
|Název|Popis|  
|----------|-----------------|  
|[SetNotificationForWaitCompletion – metoda](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|Nastaví nebo vymaže bit TASK_STATE_WAIT_COMPLETION_NOTIFICATION stavu.|  
|[NotifyDebuggerOfWaitCompletion – metoda](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|Metoda zástupný symbol používá jako cíl zarážek ladicího programu.|  
  
### <a name="fields"></a>Pole  
  
|Název|Popis|  
|----------|-----------------|  
|[m_action](../../extensibility/debugger/m-action-field.md)|Delegáta, který představuje kód na provedení v <xref:System.Threading.Tasks.Task> objektu.|  
|[m_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|Ukládá další vlastnosti <xref:System.Threading.Tasks.Task> objektu.|  
|[m_parent](../../extensibility/debugger/m-parent-field.md)|Základní pole pro <xref:System.Threading.Tasks.Task?displayProperty=fullName> nadřazených vlastnost.|  
|[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|Ukládá informace o aktuální stav <xref:System.Threading.Tasks.Task> objektu.|  
|[m_stateObject](../../extensibility/debugger/m-stateobject-field.md)|Objekt, který představuje data, která se použije v akci.|  
|[m_taskId](../../extensibility/debugger/m-taskid-field.md)|Základní pole pro <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName> vlastnost.|  
|[s_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|Identifikátor další k dispozici pro <xref:System.Threading.Tasks.Task> objektu.|  
|[TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|Znamená, že úloha byla zrušena před bylo dosaženo do stavu spuštěno nebo že úloha potvrzené jeho zrušení a byla dokončena bez výjimky.|  
|[TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|Určuje, zda je spuštěn úkol.|  
|[TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|Označuje, že úloha dokončena z důvodu neošetřené výjimky.|  
|[TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|Označuje, že úloha úspěšně dokončil provádění.|  
|[TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|Označuje, že úloha skončil jeho delegáta a implicitně čeká na dokončení úkolů připojené podřízené.|  
  
## <a name="remarks"></a>Poznámky  
 Následující vnitřní metody jsou užitečné pro modul ladicí program, protože se označit vstupu do <xref:System.Threading.Tasks.Task> spuštění kódu:  
  
-   `Execute`  
  
-   `ExecuteEntry`  
  
-   `ExecuteWithThreadLocal`  
  
-   `Finish`  
  
-   `InnerInvoke`  
  
-   `InternalWait`  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)