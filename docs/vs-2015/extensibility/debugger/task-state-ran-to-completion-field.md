---
title: Task_state_ran_to_completion – pole | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TASK_STATE_RAN_TO_COMPLETION field, Task class [.NET Framework debug engines]
ms.assetid: 0f4830af-fe0c-4141-b768-817f4e426b8c
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 08d4437a034524f6ed291dbea6e8ee0abd1f7dd5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633631"
---
# <a name="taskstaterantocompletion-field"></a>TASK_STATE_RAN_TO_COMPLETION – pole
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [task_state_ran_to_completion – pole](https://docs.microsoft.com/visualstudio/extensibility/debugger/task-state-ran-to-completion-field).  
  
Úloha byla úspěšně dokončena spuštění.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field static assembly literal int32 TASK_STATE_RAN_TO_COMPLETION = int32(0x02000000)  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud [m_stateflags –](../../extensibility/debugger/m-stateflags-field.md) pole obsahuje tuto hodnotu <xref:System.Threading.Tasks.Task.Status%2A> vrátí vlastnost <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.  
  
## <a name="see-also"></a>Viz také  
 [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)

