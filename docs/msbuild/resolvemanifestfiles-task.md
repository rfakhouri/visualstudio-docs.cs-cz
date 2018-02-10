---
title: "Resolvemanifestfiles – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveManifestFiles task [MSBuild]
- MSBuild, ResolveManifestFiles task
ms.assetid: e1e14f67-9b69-433f-94d4-a783a68676b2
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 088af1d1ef0a83b695b0a36baaa424a4926f3112
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="resolvemanifestfiles-task"></a>ResolveManifestFiles – úloha
Následující položky v procesu sestavení přeloží na soubory pro generování manifestu: vytvořené položky, závislostí, satelity, obsahu, symboly ladění a dokumentaci.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `ResolveManifestFiles` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DeploymentManifestEntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje název manifestu nasazení.|  
|`EntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje spravované sestavení nebo ClickOnce manifestu odkaz, který je vstupní bod k manifestu.|  
|`ExtraFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje další soubory.|  
|`ManagedAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje spravované sestavení.|  
|`NativeAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje nativní sestavení.|  
|`OutputAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje vygenerované sestavení.|  
|`OutputDeploymentManifestEntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje výstup nasazení manifestu vstupní bod.|  
|`OutputEntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje výstup vstupní bod.|  
|`OutputFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje výstupní soubory.|  
|`PublishFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje soubory publikovat.|  
|`SatelliteAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje satelitní sestavení.|  
|`SigningManifests`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, jsou podepsané manifesty.|  
|`TargetCulture`|Volitelné `String` parametr.<br /><br /> Určuje cílové jazykové verzi pro satelitní sestavení.|  
|`TargetFrameworkVersion`|Volitelné `String` parametr.<br /><br /> Určuje cílová verze rozhraní .NET Framework.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)