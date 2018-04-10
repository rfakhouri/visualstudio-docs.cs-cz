---
title: Getframeworkpath – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkPath task [MSBuild]
- MSBuild, GetFrameworkPath task
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
caps.latest.revision: 11
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d672a204411c58b4a164db2ff02701544f4594bf
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath – úloha
Načte cestu k [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sestavení.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `GetFrameworkPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`FrameworkVersion11Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení framework verze 1.1, pokud je k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion20Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení framework verze 2.0, pokud je k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion30Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení framework verze 3.0, pokud je k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion35Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení framework verze 3.5, pokud je k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion40Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení framework verze 4.0, pokud je k dispozici. V opačném případě vrátí `null`.|  
|`Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k nejnovější sestavení architektury, pokud budou k dispozici. V opačném případě vrátí `null`.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud několika verzích [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] jsou nainstalovaná, tato úloha vrátí verze, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] je určená ke spuštění.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `GetFrameworkPath` úloh pro cestu k uložení [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] v `FrameworkPath` vlastnost.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="FrameworkPath" />  
        </GetFrameworkPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)