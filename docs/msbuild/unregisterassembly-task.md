---
title: Unregisterassembly – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#UnregisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UnregisterAssembly task
- UnregisterAssembly task [MSBuild]
ms.assetid: 04f549dd-3591-4dda-9c3a-cf6ede9df2c3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec05565bb43d4b592515c9c4b41c969a3e677e0e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62954762"
---
# <a name="unregisterassembly-task"></a>UnregisterAssembly – úloha
Zruší registraci zadaného sestavení pro účely vzájemné spolupráce COM. Provádí opak [registerassembly – úloha](../msbuild/registerassembly-task.md).

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `UnregisterAssembly` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`Assemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje sestavení, které chcete být zrušena registrace.|
|`AssemblyListFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Obsahuje informace o stavu mezi `RegisterAssembly` úloh a `UnregisterAssembly` úloh. To zabrání pokus o zrušení registrace sestavení, které se nepodařilo zaregistrovat v úkolu `RegisterAssembly` úloh.<br /><br /> Pokud tento parametr zadán, `Assemblies` a `TypeLibFiles` parametry budou ignorovány.|
|`TypeLibFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Zruší registraci knihovny zadaný typ z určeného sestavení. **Poznámka:**  Tento parametr je jenom nutné v případě, že název souboru knihovny typů se liší od názvu sestavení.|

## <a name="remarks"></a>Poznámky
 Není nutné, aby sestavení existuje pro tento úkol k dosažení úspěchu. Při pokusu o zrušení registrace sestavení, která neexistuje, úkol proběhne úspěšně s upozorněním. K tomu dochází, protože se jedná o úlohu této úlohy můžete odebrat registraci sestavení z registru. Pokud sestavení ještě neexistuje, není v registru, a proto byla úspěšná úloha.

 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.AppDomainIsolatedTaskExtension> třída, která sama dědí z <xref:System.MarshalByRefObject> třídy. `MarshalByRefObject` Třída poskytuje stejné funkce jako <xref:Microsoft.Build.Utilities.Task> třídy, ale může být vytvořena ve vlastní doméně aplikace.

## <a name="example"></a>Příklad
 V následujícím příkladu `UnregisterAssembly` úlohy ke zrušení registrace sestavení v cestě určené `OutputPath` a `FileName` vlastnosti, pokud existuje.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <PropertyGroup>
        <OutputPath>\Output\</OutputPath>
        <FileName>MyFile.dll</FileName>
    </PropertyGroup>
    <Target Name="UnregisterAssemblies">
        <UnregisterAssembly
            Condition="Exists('$(OutputPath)$(FileName)')"
            Assemblies="$(OutputPath)$(FileName)" />
    </Target>

</Project>
```

## <a name="see-also"></a>Viz také:
- [Registerassembly – úloha](../msbuild/registerassembly-task.md)
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)