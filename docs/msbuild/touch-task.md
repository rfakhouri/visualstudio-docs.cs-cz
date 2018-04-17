---
title: Touch – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d484340e4823dc73898f3ab0eaf8afffe1c1c18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="touch-task"></a>Touch – úloha
Nastaví dobu přístup a úpravy souborů.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Touch` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AlwaysCreate`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vytvoří všechny soubory, které dosud neexistují.|  
|`Files`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje kolekci soubory tak, aby touch.|  
|`ForceTouch`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vynutí touch souboru i v případě, že jsou soubory jen pro čtení.|  
|`Time`|Volitelné `String` parametr.<br /><br /> Určuje dobu, než aktuální čas. Musí být ve formátu formátu, který se dá <xref:System.DateTime.Parse%2A> metoda.|  
|`TouchedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje kolekce položek, které byly úspěšně změněny.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Touch` úlohy lze změnit časů přístup a změny soubory zadané v `Files` položky kolekce a vloží seznam úspěšně dotyku souborů v `FilesTouched` kolekce položek.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
<ItemGroup>  
    <Files Include="File1.cs;File2.cs;File3.cs" />  
</ItemGroup>  
  
    <Target Name="TouchFiles">  
        <Touch  
            Files="@(Files)">  
            <Output  
                TaskParameter="TouchedFiles"  
                ItemName="FilesTouched"/>  
    </Touch>  
</Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)