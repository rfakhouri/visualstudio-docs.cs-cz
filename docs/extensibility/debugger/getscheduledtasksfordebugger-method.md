---
title: Metoda GetScheduledTasksForDebugger | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 20cde88083acd38df780468927faec5fbd142b67
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger – metoda
Načte pole všechny naplánované úlohy.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tento vnitřní člen nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole všechny naplánované úlohy. Každý úkol provádí nebo byl dokončen.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není bezpečná pro přístup z více vláken a neměl by se používat souběžně ostatní instance <xref:System.Threading.Tasks.TaskScheduler> by měla být volána z ladicí program jenom v případě, že ladicí program pozastavilo jiná vlákna.  
  
## <a name="see-also"></a>Viz také  
 [TaskScheduler – třída](../../extensibility/debugger/taskscheduler-class-internal-members.md)