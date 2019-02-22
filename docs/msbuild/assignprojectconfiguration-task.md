---
title: Assignprojectconfiguration – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6bc9fb3ab600c106d762d5f4ec55b6bc7117e101
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635485"
---
# <a name="assignprojectconfiguration-task"></a>Assignprojectconfiguration – úloha
Tato úloha přijímá řetězec seznamu konfigurace a přiřadí ho k zadaným projektům.

## <a name="task-parameters"></a>Parametry úlohy
 Následující tabulka popisuje parametry `AssignProjectConfiguration` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`SolutionConfigurationContents`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje řetězec XML obsahující projekt konfigurace pro každý projekt. Konfigurace jsou přiřazeny k projektům s názvem.|
|`DefaultToVcxPlatformMapping`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje seznam oddělený středníkem mapování názvů platforem používaných ve většině typů používaných *.vcxproj* soubory.<br /><br /> Příklad:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|
|`VcxToDefaultPlatformMapping`|volitelná,<br /><br /> `string` Výstupní parametr.<br /><br /> Obsahuje seznam oddělený středníkem mapování z *.vcxproj* názvů platform na názvy platformy používat ve většině typů.<br /><br /> Příklad:<br /><br /> `"Win32=AnyCPU;X64=X64"`|
|`CurrentProjectConfiguration`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje konfiguraci pro aktuální projekt.|
|`CurrentProjectPlatform`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje platformu pro aktuální projekt.|
|`OnlyReferenceAndBuildProjectsEnabledInSolutionConfiguration`|Volitelné `bool` výstupní parametr.<br /><br /> Obsahuje příznak označující, že odkazy by měly být sestaveny, i když byly zakázány v konfiguraci projektu.|
|`ShouldUnsetParentConfigurationAndPlatform`|Volitelné `bool` výstupní parametr.<br /><br /> Obsahuje příznak označující, pokud nadřazená konfigurace a platforma mají být zrušeny.|
|`OutputType`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje typ výstupu projektu.|
|`ResolveConfigurationPlatformUsingMappings`|Volitelné `bool` výstupní parametr.<br /><br /> Obsahuje příznak označující, pokud sestavení má použít výchozí mapování k řešení konfigurace a platformy předané v odkazech projektu.|
|`AssignedProjects`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam cest vyřešených odkazů.|
|`UnassignedProjects`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam referenčních položek projektu, které nelze vyřešit pomocí předem vyřešených seznamů výstupů.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)