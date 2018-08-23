---
title: Getscheduledtasksfordebugger – metoda | Dokumentace Microsoftu
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
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bf2649dbb3e2a4b5cd614f078c461217044ee08b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675305"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger – metoda
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [getscheduledtasksfordebugger – metoda](https://docs.microsoft.com/visualstudio/extensibility/debugger/getscheduledtasksfordebugger-method).  
  
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
 [Třída TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)

