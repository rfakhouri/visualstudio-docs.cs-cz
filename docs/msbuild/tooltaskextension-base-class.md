---
title: "Tooltaskextension – základní třída | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MSBuild.ToolTask.ToolCommandFailed
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 258ae433-f68a-49f1-b276-da20e3472e68
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f17c22a4f93be23ba5f29c8a225eef5bdd555c30
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="tooltaskextension-base-class"></a>ToolTaskExtension – základní třída
Dědí celou řadu úloh <xref:Microsoft.Build.Tasks.ToolTaskExtension> třídy, která dědí z <xref:Microsoft.Build.Utilities.ToolTask> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Tento řetězec dědičnosti přidá do úlohy, které jsou odvozeny od nich několik parametrů. Tyto parametry jsou uvedeny v tomto dokumentu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry základní třídy.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine> parametr.<br /><br /> Určuje rozhraní modul sestavení, která je k dispozici pro úlohy. Modul sestavení automaticky nastaví tento parametr umožňuje úloh, které se do ní zpětné volání.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine2> parametr.<br /><br /> Určuje rozhraní modul sestavení, která je k dispozici pro úlohy. Modul sestavení automaticky nastaví tento parametr umožňuje úloh, které se do ní zpětné volání.<br /><br /> Toto je užitečný vlastnost tak, aby autoři úloh, která dědí z této třídy nemají převést hodnotu z `IBuildEngine` k `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine3> parametr.<br /><br /> Určuje rozhraní modul sestavení od hostitele.|  
|<xref:Microsoft.Build.Utilities.ToolTask.EchoOff%2A>|Volitelné `bool` parametr.<br /><br /> Pokud nastavíte hodnotu `true`, tato úloha předává **/Q** k cmd.exe příkazového řádku tak, že v příkazovém řádku není kopírovány do stdout.|  
|<xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A>|Volitelné `String` parametr pole.<br /><br /> Pole dvojic proměnných prostředí, oddělených symboly rovná se. Tyto proměnné jsou předaným ke spustitelnému souboru vytvářený kromě nebo selektivně přepsání bloku regulární prostředí.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ExitCode%2A>|Volitelné `Int32` výstupní parametr jen pro čtení.<br /><br /> Určuje kód ukončení, které poskytuje provedeného příkazu. Pokud úloha protokolovat všechny chyby, ale proces měl ukončovací kód 0 (úspěch), je nastavena na hodnotu -1.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Volitelné <xref:Microsoft.Build.Framework.ITaskHost> parametr.<br /><br /> Určuje instanci objektu hostitele (může mít hodnotu null). Modul sestavení tato vlastnost nastaví, pokud hostitel IDE má přidružený objekt hostitele tuto konkrétní úlohu.|  
|<xref:Microsoft.Build.Tasks.ToolTaskExtension.Log%2A>|Volitelné <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametr jen pro čtení.<br /><br /> Získá instanci objektu <xref:Microsoft.Build.Tasks.TaskLoggingHelperExtension> třídu, která obsahuje metody protokolování úloh.|  
|<xref:Microsoft.Build.Utilities.ToolTask.LogStandardErrorAsError%2A>|Možnost `bool` parametr.<br /><br /> Pokud `true`, všechny zprávy přijaté na standardní chybový proud se zaznamenávají jako chyby.|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardErrorImportance%2A>|Volitelné `String` parametr.<br /><br /> Důležitost, ke které má být text z standard na datový proud protokolu.|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardOutputImportance%2A>|Volitelné `String` parametr.<br /><br /> Důležitost, ke které má být text z standard na datový proud protokolu.|  
|<xref:Microsoft.Build.Utilities.ToolTask.Timeout%2A>|Volitelné virtuální `Int32` parametr.<br /><br /> Určuje množství času, v milisekundách, po kterých je spustitelný soubor úlohy ukončen. Výchozí hodnota je `Int.MaxValue`, což označuje, že bez doby vypršení časového limitu. Časový limit je uvedena v milisekundách.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolExe%2A>|Volitelné virtuální `string` parametr.<br /><br /> Projekty může implementovat toto přepsání název nástroje. Úlohy může ji přepsat zachovat název nástroje.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolPath%2A>|Volitelné `string` parametr.<br /><br /> Určuje umístění, ze kterých úloha načte základní spustitelný soubor. Pokud není tento parametr zadán, použije úloha SDK Instalační cestu, která odpovídá verzi rozhraní, které běží [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|<xref:Microsoft.Build.Utilities.ToolTask.UseCommandProcessor%2A>|Volitelné `bool` parametr.<br /><br /> Pokud nastavíte hodnotu `true`, tato úloha vytvoří soubor batch pro příkazový řádek a spustí pomocí procesor příkazů místo provedení příkazu přímo.|  
|<xref:Microsoft.Build.Utilities.ToolTask.YieldDuringToolExecution%2A>|Volitelné `bool` parametr.<br /><br /> Pokud nastavíte hodnotu `true`, tato úloha poskytuje uzlu při je provádění úkolu.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)