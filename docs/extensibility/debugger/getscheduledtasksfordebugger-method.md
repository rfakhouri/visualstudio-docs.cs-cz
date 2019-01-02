---
title: Getscheduledtasksfordebugger – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d3e9b090ded89247cb69cac3d08b73fa93fc019f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53863888"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger – metoda
Načte pole všech naplánovaných úloh.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v *mscorlib.dll*)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole všech naplánovaných úloh. Každý úkol je spuštěn nebo byl dokončen.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není bezpečná a byste neměli používat souběžně s jinými instancemi <xref:System.Threading.Tasks.TaskScheduler>. Tuto metodu lze volejte z ladicího programu pouze v případě, že ladicí program byla pozastavena všechna ostatní vlákna.  
  
## <a name="see-also"></a>Viz také:  
 [Třída TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)