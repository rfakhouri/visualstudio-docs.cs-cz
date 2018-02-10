---
title: "Getframeworksdkpath – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 390df225104b8469e82d605c24e54e1025c60f37
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath – úloha
Načte cestu k [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `GetFrameworkSdkPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|Volitelné `String` jen pro čtení výstupní parametr.<br /><br /> Vrátí cestu k sadě SDK .NET verze 2.0, pokud je k dispozici. V opačném případě vrátí `String.Empty`.|  
|`FrameworkSdkVersion35Path`|Volitelné `String` jen pro čtení výstupní parametr.<br /><br /> Vrátí cestu k sadě SDK .NET verze 3.5, pokud je k dispozici. V opačném případě vrátí `String.Empty`.|  
|`FrameworkSdkVersion40Path`|Volitelné `String` jen pro čtení výstupní parametr.<br /><br /> Vrací cestu k .NET SDK verze 4.0, pokud je k dispozici. V opačném případě vrátí `String.Empty`.|  
|`Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k nejnovější sady .NET SDK, pokud se nachází všechny verze. V opačném případě vrátí `String.Empty`.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `GetFrameworkSdkPath` úloh pro cestu k uložení [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] v `SdkPath` vlastnost.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)