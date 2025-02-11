---
title: Removeduplicates – úloha | Dokumentace Microsoftu
ms.date: 03/01/2018
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 027e1f4894660b0198ed8a6df862e66e41cde409
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62811612"
---
# <a name="removeduplicates-task"></a>RemoveDuplicates – úloha
Odebere duplicitní položky z kolekce zadané položky.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `RemoveDuplicates` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`Filtered`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje kolekci položek se odebrat všechny duplicitní položky. Zachování pořadí vstupních položek udržování první instance každé duplicitní položky.|
|`Inputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Odebrat duplicitní položky z kolekce položek.|

## <a name="remarks"></a>Poznámky
 Tato úloha velká a malá písmena a není výsledkem porovnání metadata položky při určování duplicitní položky.

 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
 V následujícím příkladu `RemoveDuplicates` úloh odebrat duplicitní položky ze `MyItems` kolekci položek. Po dokončení úlohy `FilteredItems` kolekce položek obsahuje jednu položku.

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

 Následující příklad ukazuje, že `RemoveDuplicates` úlohy zachová jeho vstupní pořadí. Po dokončení úlohy `FilteredItems` kolekce položek obsahuje položky *MyFile2.cs*, *MyFile1.cs*, a *MyFile3.cs* v uvedeném pořadí.

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

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
- [Úlohy](../msbuild/msbuild-tasks.md)
