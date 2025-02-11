---
title: LC – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#LC
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, LC task
- LC task [MSBuild]
ms.assetid: d5a53472-6f2a-42b8-a6db-593ca99c9790
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fa9a210b61a1ba28d2dca2f81184b3d20a91ff7f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62817496"
---
# <a name="lc-task"></a>LC – úloha
Zabalí *LC.exe*, který generuje *.license* ze soubor *.licx* souboru. Další informace o *LC.exe*, naleznete v tématu [Lc.exe (kompilátor licencí)](/dotnet/framework/tools/lc-exe-license-compiler).

## <a name="parameters"></a>Parametry
Následující tabulka popisuje parametry `LC` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`LicenseTarget`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje spustitelný soubor, pro kterou *.licenses* soubory jsou vygenerovány.|
|`NoLogo`|Volitelné `Boolean` parametru.<br /><br /> Potlačí zobrazení úvodního nápisu společnosti Microsoft.|
|`OutputDirectory`|Volitelné `String` parametru.<br /><br /> Určuje adresář, do které chcete umístit výstup *.licenses* soubory.|
|`OutputLicense`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje název *.licenses* souboru. Pokud nezadáte název, název *.licx* soubor se používá a *.licenses* soubor umístěn v adresáři, který obsahuje *.licx* souboru.|
|`ReferencedAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Odkazované součásti pro načtení při generování Určuje, *.license* souboru.|
|`SdkToolsPath`|Volitelné `String` parametru.<br /><br /> Určuje cestu k sadě SDK nástroje, jako *resgen.exe*.|
|`Sources`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje položky, které obsahují licencovaných součástí, které mají být zahrnuty *.licenses* souboru. Další informace najdete v tématu v dokumentaci `/complist` přepínače v [Lc.exe (kompilátor licencí)](/dotnet/framework/tools/lc-exe-license-compiler).|

 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).

## <a name="example"></a>Příklad
V následujícím příkladu `LC` úkolů ke kompilaci licence.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
<!-- Item declarations, etc -->

    <Target Name="CompileLicenses">
        <LC
            Sources="@(LicxFile)"
            LicenseTarget="$(TargetFileName)"
            OutputDirectory="$(IntermediateOutputPath)"
            OutputLicenses="$(IntermediateOutputPath)$(TargetFileName).licenses"
            ReferencedAssemblies="@(ReferencePath);@(ReferenceDependencyPaths)">

            <Output
                TaskParameter="OutputLicenses"
                ItemName="CompiledLicenseFile"/>
        </LC>
    </Target>
</Project>
```

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
