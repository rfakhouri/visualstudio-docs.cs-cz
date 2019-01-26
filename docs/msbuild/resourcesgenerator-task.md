---
title: Resourcesgenerator – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b4ea1e45864918ef3b6329da04a8c6b493a50697
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013857"
---
# <a name="resourcesgenerator-task"></a>Resourcesgenerator – úloha
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> Úloh vloží jeden nebo více prostředků (*.jpg*, *.ico*, *.bmp*, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] v binárním formátu a ostatními typy rozšíření) do *.resources* souboru.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`OutputPath`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje cestu k výstupnímu adresáři. Pokud cesta není absolutní cestu, je považován za cestu, která je relativní vzhledem k kořenovém adresáři projektu.|  
|`OutputResourcesFile`|Vyžaduje **[] ITaskItem** výstupní parametr.<br /><br /> Určuje cestu a název generované *.resources* souboru. Pokud cesta není absolutní cesta, *.resources* vygenerován soubor relativní vzhledem k kořenovém adresáři projektu.|  
|`ResourcesFiles`|Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje jeden nebo více prostředků k vložení do vytvořeného *.resources* souboru.|  
  
## <a name="example"></a>Příklad  
 Následující příklad vygeneruje *.resources* soubor pomocí jediného *.bmp* prostředků. *.Bmp* prostředků se generuje na adresář, který je relativní vzhledem k kořenový adresář projektu.  
  
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
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)