---
title: Fileclassifier – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- classifying a resource set to embed in an assembly [WPF MSBuild]
- non-localizable resources [WPF MSBuild], classifying to embed in an assembly
- FileClassifier task [WPF MSBuild]
ms.assetid: 14e03310-fcc0-4bb2-a84d-cda12be66367
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9dccb229712d173e847a7205f03aad308fab224d
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55853187"
---
# <a name="fileclassifier-task"></a>Fileclassifier – úloha
<xref:Microsoft.Build.Tasks.Windows.FileClassifier> Úloh klasifikuje sadu prostředků zdroje jako ty, které budou vloženy do sestavení. Pokud prostředek není lokalizovatelné, je vložen do sestavení hlavní aplikace; v opačném případě se vloží do satelitního sestavení.

## <a name="task-parameters"></a>Parametry úlohy

|Parametr|Popis|
|---------------|-----------------|
|`CLREmbeddedResource`|Nevyužité.|
|`CLRResourceFiles`|Nevyužité.|
|`CLRSatelliteEmbeddedResource`|Nevyužité.|
|`Culture`|Volitelné **řetězec** parametru.<br /><br /> Určuje jazykovou verzi pro sestavení. Tato hodnota může být **null** Pokud je sestavení bez možnosti lokalizace. Pokud **null**, výchozí hodnota je malým hodnota, která **CultureInfo.InvariantCulture** vrátí.|
|`MainEmbeddedFiles`|Volitelné **[] ITaskItem** výstupní parametr.<br /><br /> Určuje bez možnosti lokalizace prostředky, které jsou vloženy do hlavního sestavení.|
|`OutputType`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje typ souboru se má vložit do zadané zdrojové soubory. Platné hodnoty jsou **exe**, **winexe**, nebo **knihovny**.|
|`SatelliteEmbeddedFiles`|Volitelné **[] ITaskItem** výstupní parametr.<br /><br /> Určuje lokalizovatelné soubory, které jsou vloženy do satelitního sestavení pro jazykové verze určený poskytovatelem **jazykovou verzi** parametru.|
|`SourceFiles`|Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje seznam souborů pro klasifikaci.|

## <a name="remarks"></a>Poznámky
Pokud **jazykovou verzi** parametr není nastavená, všechny prostředky, které je určené vlastností **SourceFiles** parametru jsou bez možnosti lokalizace; v opačném případě jsou lokalizovatelné, pokud jsou přidruženy k  **Lokalizovatelné** atribut, který je nastavena na **false**.

## <a name="example"></a>Příklad
V následujícím příkladu klasifikuje jeden zdrojový soubor jako prostředek a vloží jej do satelitní sestavení pro jazykovou verzi French-Canadian (fr-CA).

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.FileClassifier"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <ItemGroup>
    <Resource Include="Resource1.bmp" />
  </ItemGroup>
  <Target Name="FileClassifierTask">
    <FileClassifier
      SourceFiles="Resource1.bmp"
      Culture="fr-CA"
      OutputType="exe" />
  </Target>
</Project>
```

## <a name="see-also"></a>Viz také:
[Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)  
[Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)  
[Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)  
[Sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
