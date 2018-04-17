---
title: Requiresframework35sp1assembly – úloha | Microsoft Docs
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
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 439c42043eff69cd4f7e9e2afd2ad46499bf6063
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly – úloha
Určuje, zda aplikace vyžaduje rozhraní .NET Framework 3.5 SP1.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RequiresFramework35SP1Assembly` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Assemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje sestavení, které se odkazuje v aplikaci.|  
|`CreateDesktopShortcut`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vytvoří ikonu zástupce na ploše během instalace.|  
|`DeploymentManifestEntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje název souboru manifestu aplikace.|  
|`EntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje sestavení, který se má provést při spuštění aplikace.|  
|`ErrorReportUrl`|Volitelné `String` parametr.<br /><br /> Určuje web, který se zobrazí v dialogových oknech, které se vyskytují během instalace ClickOnce.|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje seznam souborů, které budou nasazeny, pokud je publikovaná aplikace.|  
|`ReferencedAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje sestavení, které se odkazuje v projektu.|  
|`RequiresMinimumFramework35SP1`|Volitelné `Boolean` výstupní parametr.<br /><br /> Pokud `true`, aplikace vyžaduje rozhraní .NET Framework 3.5 SP1.|  
|`SigningManifests`|Volitelné `Boolean` výstupní parametr.<br /><br /> Pokud `true`, jsou podepsané manifesty ClickOnce.|  
|`SuiteName`|Volitelné `String` parametr.<br /><br /> Určuje název složky na **spustit** nabídky, ve kterém bude aplikace nainstalována.|  
|`TargetFrameworkVersion`|Volitelné `String` parametr.<br /><br /> Určuje verzi rozhraní .NET Framework který tato aplikace cíle.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)