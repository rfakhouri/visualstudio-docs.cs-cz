---
title: "Assignprojectconfiguration – úloha | Microsoft Docs"
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
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7a4a803647afac9de77096e4a16d41987ff70c4f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="assignprojectconfiguration-task"></a>AssignProjectConfiguration – úloha
Tato úloha přijímá konfiguračním řetězce seznamu a přiřadí zadaný projekty.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AssignProjectConfiguration` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`SolutionConfigurationContents`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje řetězec XML obsahující projekt konfiguraci pro každý projekt. Konfigurace jsou přiřazeny k pojmenované projekty.|  
|`DefaultToVcxPlatformMapping`|Volitelné `string` výstupní parametr.<br /><br /> Obsahuje seznam mapování z názvů platform používaných oddělený středníkem<br /><br /> Většina typy těm, které jsou používané VCXPROJ soubory.<br /><br /> Příklad:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|  
|`VcxToDefaultPlatformMapping`|Nepovinné<br /><br /> `string`výstupní parametr.<br /><br /> Obsahuje seznam mapování z názvů platform VCXPROJ platformy názvy používané většinu typů oddělených středníky.<br /><br /> Příklad:<br /><br /> `"Win32=AnyCPU;X64=X64"`|  
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