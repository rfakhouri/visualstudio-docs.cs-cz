---
title: Findunderpath – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c22e2465b79faa68f8789cefeeb181c2e15b73b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62539704"
---
# <a name="findunderpath-task"></a>FindUnderPath – úloha
Určuje, které položky v kolekci určenou položku mají cesty, které jsou v nebo nižší než zadané složky.

## <a name="parameters"></a>Parametry
Následující tabulka popisuje parametry `FindUnderPath` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje soubory, jejichž cesty by měly být porovnány s Cesta zadaná položkou `Path` parametru.|
|`InPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které nebyly nalezeny v zadané cestě.|
|`OutOfPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které nebyly nalezeny v zadané cestě.|
|`Path`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje cestu složky pro použití jako odkaz.|
|`UpdateToAbsolutePaths`|Volitelné `Boolean` parametru.<br /><br /> Při hodnotě true se cesty výstupní položky jsou aktualizované tak být absolutní cesty.|

## <a name="remarks"></a>Poznámky
Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
V následujícím příkladu `FindUnderPath` úloh k určení, pokud soubory obsažené v `MyFiles` položky mají cesty, které existují v cestě určené `SearchPath` vlastnost. Po dokončení úlohy `FilesNotFoundInPath` obsahuje položku *File1.txt* souboru a `FilesFoundInPath` položka obsahuje *Soubor2.txt* souboru.

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

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
