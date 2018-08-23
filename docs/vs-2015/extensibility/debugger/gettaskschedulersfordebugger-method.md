---
title: Gettaskschedulersfordebugger – metoda | Dokumentace Microsoftu
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
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3d2bc798575cafbeb04837c3065d69b76ee872df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675399"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger – metoda
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [gettaskschedulersfordebugger – metoda](https://docs.microsoft.com/visualstudio/extensibility/debugger/gettaskschedulersfordebugger-method).  
  
Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou aktuálně aktivní v tomto <xref:System.AppDomain>.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není bezpečná a by neměl nelze použít současně s jinými instancemi <xref:System.Threading.Tasks.TaskScheduler>. By měla být volána z ladicího programu pouze v případě, že ladicí program byla pozastavena všechna ostatní vlákna.  
  
## <a name="see-also"></a>Viz také  
 [Třída TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)

