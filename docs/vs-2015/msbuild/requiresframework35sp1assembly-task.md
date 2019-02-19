---
title: Requiresframework35sp1assembly – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 737f7ece16b6947e2dd4ba017b8928560413b2b2
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54778747"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Určuje, zda aplikace požaduje instalaci rozhraní .NET Framework 3.5 SP1.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RequiresFramework35SP1Assembly` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Assemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje sestavení, které jsou odkazovány v aplikaci.|  
|`CreateDesktopShortcut`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, vytvoří ikonu zástupce na ploše během instalace.|  
|`DeploymentManifestEntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje název souboru manifestu aplikace.|  
|`EntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje sestavení, která má být spuštěn při spuštění aplikace.|  
|`ErrorReportUrl`|Volitelné `String` parametru.<br /><br /> Určuje web, který se zobrazí v dialogových oknech, které se vyskytují během instalace ClickOnce.|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje seznam souborů, které se nasadí, když je aplikace publikována.|  
|`ReferencedAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje sestavení, které je odkazováno v projektu.|  
|`RequiresMinimumFramework35SP1`|Volitelné `Boolean` výstupní parametr.<br /><br /> Pokud `true`, aplikace požaduje instalaci rozhraní .NET Framework 3.5 SP1.|  
|`SigningManifests`|Volitelné `Boolean` výstupní parametr.<br /><br /> Pokud `true`, jsou podepsané manifesty ClickOnce.|  
|`SuiteName`|Volitelné `String` parametru.<br /><br /> Určuje název složky **Start** nabídka, ve kterém se aplikace nainstaluje.|  
|`TargetFrameworkVersion`|Volitelné `String` parametru.<br /><br /> Určuje verzi rozhraní .NET Framework, který tato aplikace cílena.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
