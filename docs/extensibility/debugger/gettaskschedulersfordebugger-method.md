---
title: Gettaskschedulersfordebugger – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 76229d86c973c9ef512ecf5039ae420085129160
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029242"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger – metoda
Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v *mscorlib.dll*)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou aktuálně aktivní v tomto <xref:System.AppDomain>.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není bezpečná a byste neměli používat souběžně s jinými instancemi <xref:System.Threading.Tasks.TaskScheduler>. Tuto metodu lze volejte z ladicího programu pouze v případě, že ladicí program byla pozastavena všechna ostatní vlákna.  
  
## <a name="see-also"></a>Viz také:  
 [Třída TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)