---
title: "Removeduplicates – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#RemoveDuplicates
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RemoveDuplicates task
- RemoveDuplicates task [MSBuild]
ms.assetid: 481cbab6-73ff-488c-aba5-2c09f9eb1e04
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b735b706ec7c258e168c75dcfd8b456df23a021e
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="removeduplicates-task"></a>RemoveDuplicates – úloha
Odebere duplicitní položky z kolekce zadanou položku.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RemoveDuplicates` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Filtered`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje kolekci položky s všechny duplicitní položky odebrat.|  
|`Inputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Odeberte duplicitní položky z kolekce položek.|  
  
## <a name="remarks"></a>Poznámky  
 Tato úloha je malá a velká písmena a nelze použít k porovnání metadata položky při určování duplicitní položky.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `RemoveDuplicates` úloh odeberte duplicitní položky ze `MyItems` kolekce položek. Po dokončení úlohy `FilteredItems` položky kolekce obsahuje jednu položku.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyItems Include="MyFile.cs"/>  
        <MyItems Include="MyFile.cs">  
            <Culture>fr</Culture>  
        </MyItems>  
        <MyItems Include="myfile.cs"/>  
    </ItemGroup>  
  
    <Target Name="RemoveDuplicateItems">  
        <RemoveDuplicates  
            Inputs="@(MyItems)">  
            <Output  
                TaskParameter="Filtered"  
                ItemName="FilteredItems"/>  
        </RemoveDuplicates>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)