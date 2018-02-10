---
title: "Findunderpath – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#FindUnderPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FindUnderPath task
- FindUnderPath task [MSBuild]
ms.assetid: 3c6d58b0-36e8-47aa-bfca-b73dd2045d91
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c4c4e3cf9bbab48749cf3f0aae99057d9ade2b05
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="findunderpath-task"></a>FindUnderPath – úloha
Určuje, které položky v kolekci určenou položku mají cesty, které jsou v nebo níže v zadané složce.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `FindUnderPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje soubory, jejichž cesty se porovná s cestu určenou položkou `Path` parametr.|  
|`InPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které nebyly nalezeny v zadané cestě.|  
|`OutOfPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které nebyly nalezeny v zadané cestě.|  
|`Path`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje cestu složky chcete použít jako odkaz.|  
|`UpdateToAbsolutePaths`|Volitelné `Boolean` parametr.<br /><br /> V případě hodnoty true cesty výstupní položky se aktualizují jako absolutní cesty.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `FindUnderPath` úloh k určení, pokud soubory obsažené v `MyFiles` položky mít cesty, které existují v cestě určeného `SearchPath` vlastnost. Po dokončení úlohy `FilesNotFoundInPath` položka obsahuje `File1.txt` souboru a `FilesFoundInPath` položka obsahuje `File2.txt` souboru.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <MyFiles Include="C:\File1.txt" />  
        <MyFiles Include="C:\Projects\MyProject\File2.txt" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <SearchPath>C:\Projects\MyProject</SearchPath>  
    </PropertyGroup>  
  
    <Target Name="FindFiles">  
        <FindUnderPath  
            Files="@(MyFiles)"  
            Path="$(SearchPath)">  
            <Output  
                TaskParameter="InPath"  
                ItemName="FilesFoundInPath" />  
            <Output  
                TaskParameter="OutOfPath"  
                ItemName="FilesNotFoundInPath" />  
        </FindUnderPath>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)