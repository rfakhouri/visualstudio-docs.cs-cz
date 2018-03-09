---
title: "Removeduplicates – úloha | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2018
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
ms.openlocfilehash: ce3271b84d4d6bbb4f7905294d0c9fad678c1b8f
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="removeduplicates-task"></a>RemoveDuplicates – úloha
Odebere duplicitní položky z kolekce zadanou položku.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RemoveDuplicates` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Filtered`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje kolekci položky s všechny duplicitní položky odebrat. Pořadí vstupních položek je zachovaná, udržování první instance každé duplicitní položky.|  
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

 Následující příklad ukazuje, že `RemoveDuplicates` zachovává jeho vstupní pořadí úkolů. Po dokončení úlohy `FilteredItems` kolekce položek obsahuje položky "MyFile2.cs", "MyFile1.cs" a "MyFile3.cs" v tomto pořadí.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyItems Include="MyFile2.cs"/>  
        <MyItems Include="MyFile1.cs" />  
        <MyItems Include="MyFile3.cs" />  
        <MyItems Include="myfile1.cs"/>  
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
