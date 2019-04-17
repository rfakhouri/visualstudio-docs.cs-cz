---
title: Removeduplicates – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 73ad829c86305ff4d9a54025467e262d56e24dbc
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59654513"
---
# <a name="removeduplicates-task"></a>RemoveDuplicates – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Odebere duplicitní položky z kolekce zadané položky.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RemoveDuplicates` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Filtered`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje kolekci položek se odebrat všechny duplicitní položky.|  
|`Inputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Odebrat duplicitní položky z kolekce položek.|  
  
## <a name="remarks"></a>Poznámky  
 Tato úloha velká a malá písmena a není výsledkem porovnání metadata položky při určování duplicitní položky.  
  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `RemoveDuplicates` úloh odebrat duplicitní položky ze `MyItems` kolekci položek. Po dokončení úlohy `FilteredItems` kolekce položek obsahuje jednu položku.  
  
```  
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
