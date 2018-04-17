---
title: Resolvemanifestfiles – úloha | Microsoft Docs
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
- ResolveManifestFiles task [MSBuild]
- MSBuild, ResolveManifestFiles task
ms.assetid: e1e14f67-9b69-433f-94d4-a783a68676b2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 07a3753180ed568db19c523fd89901995e048606
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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