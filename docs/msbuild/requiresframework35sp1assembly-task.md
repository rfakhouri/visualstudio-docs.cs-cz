---
title: Requiresframework35sp1assembly – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56c1e640c3b6f7a285c10b2487f9758520facf11
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608640"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly – úloha
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

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)