---
title: Úloha ZipDirectory | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ZipDirectory
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ZipDirectory task [MSBuild]
- MSBuild, ZipDirectory task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2188ef3026e36d5c97cf35cd29362411c473973e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777473"
---
# <a name="zipdirectory-task"></a>ZipDirectory úkolu
Vytvoří *ZIP* archiv z obsah adresáře.

>[!NOTE]
>`ZipDirectory` Úloh je k dispozici v MSBuild 15.8 a vyšší pouze.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `ZipDirectory` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`DestinationFile`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametr<br /><br /> Úplná cesta k *ZIP* souboru se má vytvořit.|
|`Overwrite`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, přeskočí se přepsat cílový soubor, pokud existuje. Výchozí hodnota je `false`.|
|`SourceDirectory`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje adresář, který chcete vytvořit *ZIP* z archivu.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
 Následující příklad vytvoří *ZIP* archiv z výstupního adresáře po sestavení projektu.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip" />
    </Target>

</Project>
```

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
