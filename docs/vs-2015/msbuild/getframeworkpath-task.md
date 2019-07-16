---
title: Getframeworkpath – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
manager: jillfra
ms.openlocfilehash: 2b528d0a4971d1d070c69d12cdb9a693d9a30f20
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149494"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
