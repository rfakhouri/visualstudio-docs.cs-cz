---
title: Getframeworksdkpath – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15346bdd7c049a152a5a2d1668891f9d97da31fe
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644351"
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath – úloha
Načte cestu k [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].

## <a name="task-parameters"></a>Parametry úlohy
Následující tabulka popisuje parametry `GetFrameworkSdkPath` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`FrameworkSdkVersion20Path`|Volitelné `String` jen pro čtení výstupního parametru.<br /><br /> Vrátí cestu k sadě .NET SDK verze 2.0, pokud jsou k dispozici. V opačném případě vrátí `String.Empty`.|
|`FrameworkSdkVersion35Path`|Volitelné `String` jen pro čtení výstupního parametru.<br /><br /> Vrátí cestu k sadě .NET SDK verze 3.5, pokud jsou k dispozici. V opačném případě vrátí `String.Empty`.|
|`FrameworkSdkVersion40Path`|Volitelné `String` jen pro čtení výstupního parametru.<br /><br /> Vrátí cestu k sadě .NET SDK verze 4.0, pokud jsou k dispozici. V opačném případě vrátí `String.Empty`.|
|`Path`|Volitelné `String` výstupní parametr.<br /><br /> Obsahuje cestu k nejnovější sady .NET SDK, pokud je k dispozici žádné verze. V opačném případě vrátí `String.Empty`.|

## <a name="remarks"></a>Poznámky
Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
V následujícím příkladu `GetFrameworkSdkPath` úloh pro uložení této cesty do [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] v `SdkPath` vlastnost.

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

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
