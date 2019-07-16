---
title: Getscheduledtasksfordebugger – metoda | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b4ac6fa753be7672f1e698bda231bd11217c10d4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152732"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger – metoda
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte pole všech naplánovaných úloh.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole všech naplánovaných úloh. Každý úkol je spuštěn nebo byl dokončen.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není bezpečná a by neměl nelze použít současně s jinými instancemi <xref:System.Threading.Tasks.TaskScheduler> by měla být volána z ladicího programu pouze v případě, že ladicí program byla pozastavena všechna ostatní vlákna.  
  
## <a name="see-also"></a>Viz také  
 [TaskScheduler – třída](../../extensibility/debugger/taskscheduler-class-internal-members.md)
