---
title: Assignprojectconfiguration – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 457e0efa3a05f9ebbc3a2a99f6412e0ea49bfaf0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assignprojectconfiguration-task"></a>AssignProjectConfiguration – úloha
Tato úloha přijímá konfiguračním řetězce seznamu a přiřadí zadaný projekty.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AssignProjectConfiguration` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`SolutionConfigurationContents`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje řetězec XML obsahující projekt konfiguraci pro každý projekt. Konfigurace jsou přiřazeny k pojmenované projekty.|  
|`DefaultToVcxPlatformMapping`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje seznam mapování z názvů platform používaných oddělený středníkem<br /><br /> Většina typy těm, které jsou používané VCXPROJ soubory.<br /><br /> Příklad:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|  
|`VcxToDefaultPlatformMapping`|Nepovinné<br /><br /> `string` Výstupní parametr.<br /><br /> Obsahuje seznam mapování z názvů platform VCXPROJ platformy názvy používané většinu typů oddělených středníky.<br /><br /> Příklad:<br /><br /> `"Win32=AnyCPU;X64=X64"`|  
|`CurrentProjectConfiguration`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje konfiguraci pro aktuální projekt.|  
|`CurrentProjectPlatform`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje platforma pro aktuální projekt.|  
|`OnlyReferenceAndBuildProjectsEnabledInSolutionConfiguration`|Volitelné `bool` výstupní parametr.<br /><br /> Obsahuje příznak, který udává, že by měly být vytvořeny odkazy i v případě, že byla zakázána v konfiguraci projektu.|  
|`ShouldUnsetParentConfigurationAndPlatform`|Volitelné `bool` výstupní parametr.<br /><br /> Obsahuje příznak, který udává, pokud by měla být platformu a nadřazené konfiguraci nastavení.|  
|`OutputType`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje výstupní typ pro projekt.|  
|`ResolveConfigurationPlatformUsingMappings`|Volitelné `bool` výstupní parametr.<br /><br /> Obsahuje příznak, který udává, pokud sestavení by měl použít výchozí mapování k vyřešení konfigurace a platforma předaný v odkazy na projekt.|  
|`AssignedProjects`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam přeložit odkaz na cesty.|  
|`UnassignedProjects`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam položek odkaz na projekt, které nebylo možné přeložit pomocí předem přeložit seznam výstupy.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)