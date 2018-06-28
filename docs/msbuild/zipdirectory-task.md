---
title: Úloha ZipDirectory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0d818c6ffbef8502634e80903f6cf1dc853e6ce
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059326"
---
# <a name="zipdirectory-task"></a>ZipDirectory úloh
Vytvoří `.zip` archivu z obsahu adresáře.

**Poznámka:** `ZipDirectory` úloh je k dispozici v MSBuild 15.8 a výše pouze.
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `ZipDirectory` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DestinationFile`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr<br /><br /> Úplná cesta k `.zip` souboru vytvořte.|
|`Overwrite`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přeskočí cílový soubor se přepíše, pokud existuje. Použije se výchozí hodnota `false`.|
|`SourceDirectory`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje adresář, který chcete vytvořit `.zip` z archivu.|
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří `.zip` archivu z výstupního adresáře po sestavení projektu.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
      <ZipOutputPath>$(MSBuildProjectDirectory)</ZipOutputPath>
    </PropertyGroup>

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip">
        />
    </Target>

</Project>
```
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
