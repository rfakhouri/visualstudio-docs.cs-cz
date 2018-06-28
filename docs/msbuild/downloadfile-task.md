---
title: Úloha DownloadFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#DownloadFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- DownloadFile task [MSBuild]
- MSBuild, DownloadFile task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f8a5a5ab1f1ca86b0378b14e666c8569a01fb27
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059328"
---
# <a name="downloadfile-task"></a>DownloadFile úloh
Stáhne zadané soubory pomocí technologie Hyper-Text přenos protokol (HTTP).

**Poznámka:** `DownloadFile` úloh je k dispozici v MSBuild 15.8 a výše pouze.
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `DownloadFile` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DestinationFileName`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr<br /><br /> Název, který se má použít pro stažený soubor.  Ve výchozím nastavení je název souboru odvozený od `SourceUrl` nebo vzdálený server.|
|`DestinationFolder`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje cílovou složku ke stažení souboru.  Pokud složka se vytvoří, pokud neexistuje.|
|`DownloadedFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje soubor, který byl stažen.|
|`Retries`|Volitelné `Int32` parametr.<br /><br /> Určuje, jak často má provést při stahování, pokud všechny předchozí pokusy se nezdařily. Výchozím nastavením je nula.|  
|`RetryDelayMilliseconds`|Volitelné `Int32` parametr.<br /><br /> Určuje zpoždění v milisekundách mezi všechny nezbytné opakování. Výchozí hodnota je do 5 000.|  
|`SkipUnchangedFiles`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přeskočí stahování souborů, které jsou stejné. Použije se výchozí hodnota `true`. `DownloadFile` Úloh zvažuje soubory být beze změny, pokud mají stejnou velikost a stejný čas podle vzdáleného serveru poslední změny. **Poznámka:** ne všechny servery HTTP označuje datum poslední změny souborů způsobí, že soubor být znovu stažena.|
|`SourceUrl`|Požadované `String` parametr.<br /><br /> Určuje adresu URL pro stahování.|
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu soubory ke stažení souboru a zahrnuje ho `Content` položek než začnete vytvářet projekt.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>  
      <MyUrl>https://raw.githubusercontent.com/Microsoft/msbuild/master/LICENSE</MyUrl>
    </PropertyGroup>  

    <Target Name="DownloadContentFiles" BeforeTargets="Build">
        <DownloadFile
            SourceUrl="$(MyUrl)"
            DestinationFolder="$(MSBuildProjectDirectory)">
        <Output TaskParameter="DownloadedFile" ItemName="Content" />
      </DownloadFile>
    </Target>

</Project>
```
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
