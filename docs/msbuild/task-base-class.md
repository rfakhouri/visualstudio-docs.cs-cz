---
title: Task – základní třída | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 361ff48c1363fc2e736f01c983b32a3ee229a839
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="task-base-class"></a>Třída Base úlohy
Nakonec dědí celou řadu úloh <xref:Microsoft.Build.Utilities.Task> třídy. Tato třída přidává několik parametrů na úlohy, které jsou odvozeny od nich. Tyto parametry jsou uvedeny v tomto dokumentu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry této základní třídy.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine> parametr.<br /><br /> Určuje rozhraní modul sestavení, která je k dispozici pro úlohy. Modul sestavení automaticky nastaví tento parametr umožňuje úloh, které se do ní zpětné volání.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine2> parametr.<br /><br /> Určuje rozhraní modul sestavení, která je k dispozici pro úlohy. Modul sestavení automaticky nastaví tento parametr umožňuje úloh, které se do ní zpětné volání.<br /><br /> Toto je užitečný vlastnost tak, aby autoři úloh, která dědí z této třídy nemají převést hodnotu z `IBuildEngine` k `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine3> parametr.<br /><br /> Určuje rozhraní modul sestavení od hostitele.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Volitelné <xref:Microsoft.Build.Framework.ITaskHost> parametr.<br /><br /> Určuje instanci objektu hostitele (může mít hodnotu null). Modul sestavení tato vlastnost nastaví, pokud hostitel IDE má přidružený objekt hostitele tuto konkrétní úlohu.|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|Volitelné <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametr jen pro čtení.<br /><br /> Pomocný objekt protokolování...|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)