---
title: Taskextension – základní třída | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tool task base class
- tool task base class [MSBuild]
ms.assetid: 08bb8059-b7e2-4565-89ba-d9034d4f0e16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 13835d82fa331f25060eaa96d9317eeb1226efea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="taskextension-base-class"></a>TaskExtension – základní třída
Dědí celou řadu úloh <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Tento řetězec dědičnosti přidá do úlohy, které jsou odvozeny od nich několik parametrů. Tyto parametry jsou uvedeny v tomto dokumentu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry základní třídy.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine> parametr.<br /><br /> Určuje rozhraní modul sestavení, která je k dispozici pro úlohy. Modul sestavení automaticky nastaví tento parametr umožňuje úloh, které se do ní zpětné volání.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine2> parametr.<br /><br /> Určuje rozhraní modul sestavení, která je k dispozici pro úlohy. Modul sestavení automaticky nastaví tento parametr umožňuje úloh, které se do ní zpětné volání.<br /><br /> Toto je užitečný vlastnost tak, aby autoři úloh, která dědí z této třídy nemají převést hodnotu z `IBuildEngine` k `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine3> parametr.<br /><br /> Určuje rozhraní modul sestavení od hostitele.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Volitelné <xref:Microsoft.Build.Framework.ITaskHost> parametr.<br /><br /> Určuje instanci objektu hostitele (může mít hodnotu null). Modul sestavení tato vlastnost nastaví, pokud hostitel IDE má přidružený objekt hostitele tuto konkrétní úlohu.|  
|<xref:Microsoft.Build.Tasks.TaskExtension.Log%2A>|Volitelné <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametr jen pro čtení.<br /><br /> Získá `TaskLoggingHelperExtension` objekt, který obsahuje metody protokolování úloh.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)