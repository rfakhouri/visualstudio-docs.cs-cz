---
title: Getframeworkpath – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0d7bf2432e37278c924d1604e735feec7b848b01
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747559"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath – úloha
Načte cestu k sestavení rozhraní .NET Framework.

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
Pokud nainstalovaných několik verzí rozhraní .NET Framework, tato úloha vrátí verzi, která [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] je navržen pro spouštění na.

Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
V následujícím příkladu `GetFrameworkPath` úloh pro uložení této cesty v rozhraní .NET Framework `FrameworkPath` vlastnost.

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

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
