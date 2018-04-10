---
title: Task – základní třída | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
caps.latest.revision: 6
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c27077237b3fd173be0ba368d1b34e54939ea1e2
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
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