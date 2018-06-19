---
title: Fileclassifier – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a754f5aef53eed581deb9ccafa0bf5c453d8086d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568347"
---
# <a name="fileclassifier-task"></a>FileClassifier – úloha
<xref:Microsoft.Build.Tasks.Windows.FileClassifier> Úloh klasifikuje sadu zdroje prostředků jako ty, které budou vloženy do sestavení. Pokud prostředek není lokalizovatelný, se vloží do hlavní aplikace sestavení; jinak je integrovaný do satelitní sestavení.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`CLREmbeddedResource`|Nepoužívá se.|  
|`CLRResourceFiles`|Nepoužívá se.|  
|`CLRSatelliteEmbeddedResource`|Nepoužívá se.|  
|`Culture`|Volitelné **řetězec** parametr.<br /><br /> Určuje jazykovou verzi pro sestavení. Tato hodnota může být **null** Pokud nepřekládá sestavení. Pokud **null**, výchozí hodnota je malá hodnota, která **CultureInfo.InvariantCulture** vrátí.|  
|`MainEmbeddedFiles`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Určuje nepřekládá prostředky, které jsou vloženy do hlavní sestavení.|  
|`OutputType`|Požadované **řetězec** parametr.<br /><br /> Určuje typ souboru pro vložení souborů do zadaného zdroje. Platné hodnoty jsou **exe**, **winexe**, nebo **knihovny**.|  
|`SatelliteEmbeddedFiles`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Určuje možnosti lokalizace soubory, které jsou vloženy do satelitní sestavení pro jazykovou verzi určeného **jazykovou verzi** parametr.|  
|`SourceFiles`|Požadované **[ITaskItem]** parametr.<br /><br /> Určuje seznam souborů ke klasifikaci.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud **jazykovou verzi** není nastavený parametr, všechny prostředky, které jsou určeny pomocí **SourceFiles** parametr nepřekládá; jinak, jsou lokalizovatelný, pokud jsou přidruženy  **Lokalizovatelný** atribut, který je nastaven na **false**.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu klasifikuje jeden zdrojový soubor jako prostředek a potom se vloží do satelitní sestavení pro jazykovou verzi French-Canadian (fr-CA).  
  
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
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)