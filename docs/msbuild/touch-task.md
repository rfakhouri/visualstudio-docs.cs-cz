---
title: "Touch – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
caps.latest.revision: "17"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 459cea5aa39ae718fddbd97114528b45ddc460c6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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