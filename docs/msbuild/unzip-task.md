---
title: Rozbalte úloh | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Unzip
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Unzip task [MSBuild]
- MSBuild, Unzip task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a46f2a079cc35e6c1add9e53abdcbdd283ddb9e
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059327"
---
# <a name="unzip-task"></a>Unzip – úloha
Unzips `.zip` archivu do zadaného umístění.

**Poznámka:** `Unzip` úloh je k dispozici v MSBuild 15.8 a výše pouze.
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Unzip` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DestinationFolder`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr<br /><br /> Určuje cílovou složku a rozbalit soubor.|
|`OverwriteReadOnlyFiles`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přepíše soubory jen pro čtení. Použije se výchozí hodnota `false`.|
|`SkipUnchangedFiles`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přeskočí rozbalení soubory, které jsou stejné. Použije se výchozí hodnota `true`. Úloha `Unzip` považuje soubory za nezměněné, pokud mají stejnou velikost a je uveden stejný čas poslední aktualizace.|
|`SourceFiles`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje jeden nebo více soubor dekomprimovat. Při zadávání více souborů jsou rozbalené v pořadí do stejné složky.|
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu unzips archivu a přepíše všechny soubory jen pro čtení.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="UnzipArchive" BeforeTargets="Build">
        <Unzip
            SourceFiles="MyArchive.zip"
            DestinationFolder="$(OutputPath)\unzipped"
            OverwriteReadOnlyFiles="true"
        />
    </Target>

</Project>
```
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
