---
title: ResourcesGenerator – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2591bef1dc286acd11db4840b43410265d7aa063
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator – úloha
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> Úloh vloží jeden nebo více prostředků (.ico, který JPG, BMP, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] v binárním formátu a jinými typy rozšíření) do souboru .resources.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`OutputPath`|Požadované **řetězec** parametr.<br /><br /> Určuje cestu k výstupnímu adresáři. Pokud cesta není absolutní cesta, bude považován za cestu, která je relativní vzhledem ke kořenovém adresáři projektu.|  
|`OutputResourcesFile`|Požadované **[ITaskItem]** výstupní parametr.<br /><br /> Určuje cestu a název generovaného zdrojového souboru. Pokud cesta není absolutní cesta, vygeneruje se souboru .resources relativně k kořenovém adresáři projektu.|  
|`ResourcesFiles`|Požadované **[ITaskItem]** parametr.<br /><br /> Určuje jeden nebo více zdrojů pro vložení do generovaného zdrojového souboru.|  
  
## <a name="example"></a>Příklad  
 Následující příklad generuje soubor .resources s .bmp jeden prostředek. Generuje se .bmp prostředků do adresáře, který je relativní vzhledem ke kořenový adresář projektu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)