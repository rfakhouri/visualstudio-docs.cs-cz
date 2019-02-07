---
title: CreateProperty – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ea5dc0d2516ab7cf3c4e26b5e8f39328eabe47cb
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55853440"
---
# <a name="createproperty-task"></a>CreateProperty – úloha
Naplní hodnoty předané vlastnosti. Díky tomu hodnoty zkopírovány z jedné vlastnosti nebo řetězec do druhého.

## <a name="attributes"></a>Atributy
Následující tabulka popisuje parametry `CreateProperty` úloh.

| Parametr | Popis |
|------------------| - |
| `Value` | Volitelné `String` výstupní parametr.<br /><br /> Určuje hodnotu zkopírujte do nové vlastnosti. |
| `ValueSetByTask` | Volitelné `String` výstupní parametr.<br /><br /> Obsahuje stejnou hodnotu jako `Value` parametru. Tento parametr použijte jenom v případě, že chcete, abyste se vyhnuli nutnosti nastavit vlastnost výstupu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] při vynechává ohraničující cíl protože výstupy jsou aktuální. |

## <a name="remarks"></a>Poznámky
Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
V následujícím příkladu `CreateProperty` úkolu k vytvoření `NewFile` vlastnost pomocí kombinace hodnot `SourceFilename` a `SourceFileExtension` vlastnost.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
        <SourceFilename>Module1</SourceFilename>
        <SourceFileExtension>vb</SourceFileExtension>
    </PropertyGroup>

    <Target Name="CreateProperties">

        <CreateProperty
            Value="$(SourceFilename).$(SourceFileExtension)">
            <Output
                TaskParameter="Value"
                PropertyName="NewFile" />
        </CreateProperty>

    </Target>

</Project>
```

Po spuštění projektu, hodnota `NewFile` vlastnost *Module1.vb*.

## <a name="see-also"></a>Viz také:
[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)  
[Úlohy](../msbuild/msbuild-tasks.md)
