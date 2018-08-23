---
title: Getframeworkpath – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
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
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 792c6fd47882e0ff116859c80e3e406e875bf5fe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629630"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [getframeworkpath – úloha](https://docs.microsoft.com/visualstudio/msbuild/getframeworkpath-task).  
  
  
Načte cestu k [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sestavení.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `GetFrameworkPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`FrameworkVersion11Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení rozhraní framework verze 1.1, pokud jsou k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion20Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení rozhraní framework verze 2.0, pokud jsou k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion30Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení rozhraní framework verze 3.0, pokud jsou k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion35Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení rozhraní framework verze 3.5, pokud jsou k dispozici. V opačném případě vrátí `null`.|  
|`FrameworkVersion40Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k sestavení rozhraní framework verze 4.0, pokud jsou k dispozici. V opačném případě vrátí `null`.|  
|`Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k nejnovější sestavení rozhraní, pokud jsou nějaké k dispozici. V opačném případě vrátí `null`.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud se několik verzí [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] jsou nainstalované, tato úloha vrátí verzi, která [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] je navržen pro spouštění na.  
  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `GetFrameworkPath` úloh pro uložení této cesty do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] v `FrameworkPath` vlastnost.  
  
```  
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



