---
title: Metoda GetTaskSchedulersForDebugger | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 474d809f36d21b254dbb8bf302cd21bc83db88a9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger – metoda
Načte pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tento vnitřní člen nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní v tomto <xref:System.AppDomain>.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není bezpečná pro přístup z více vláken a neměl by se používat souběžně ostatní instance <xref:System.Threading.Tasks.TaskScheduler>. Z ladicí program by měla být volána pouze v případě, že ladicí program pozastavilo jiná vlákna.  
  
## <a name="see-also"></a>Viz také  
 [TaskScheduler – třída](../../extensibility/debugger/taskscheduler-class-internal-members.md)