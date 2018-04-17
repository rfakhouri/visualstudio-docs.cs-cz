---
title: Assigntargetpath – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e49e03f2bb48ba68559bb49725780e9bf4c0ff4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assigntargetpath-task"></a>AssignTargetPath – úloha
Tato úloha přijímá seznam souborů a přidá `<TargetPath>` atributy, když už nejsou zadané.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AssignTargetPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`RootFolder`|Volitelné `string` vstupní parametr.<br /><br /> Obsahuje cestu ke složce, která obsahuje cílové odkazy.|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` vstupní parametr.<br /><br /> Příchozí seznam souborů, které obsahuje.|  
|`AssignedFiles`|Nepovinné<br /><br /> <xref:Microsoft.Build.Framework.ITaskItem> `[]` Výstupní parametr.<br /><br /> Výsledný seznam souborů, které obsahuje.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad spustí `AssignTargetPath` úlohy konfigurace projektu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyProject">  
        <AssignTargetPath  
RootFolder="Resources"  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
        </AssignTargetPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)