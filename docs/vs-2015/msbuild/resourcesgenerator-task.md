---
title: Resourcesgenerator – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
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
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fa8b438727160bb5a752643f7ef9791ca5e09245
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682140"
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> Úloh vloží jeden nebo více prostředků (JPG, ICO, BMP, [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] v binárním formátu a ostatními typy rozšíření) do souboru .resources.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`OutputPath`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje cestu k výstupnímu adresáři. Pokud cesta není absolutní cestu, je považován za cestu, která je relativní vzhledem k kořenovém adresáři projektu.|  
|`OutputResourcesFile`|Vyžaduje **[] ITaskItem** výstupní parametr.<br /><br /> Určuje cestu a název souboru .resources generovaného. Pokud cesta není absolutní cestu, vygeneruje se soubor .resources vzhledem k kořenovém adresáři projektu.|  
|`ResourcesFiles`|Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje jeden nebo více prostředků k vložení do generovaného zdrojového souboru.|  
  
## <a name="example"></a>Příklad  
 Následující příklad generuje soubor .resources, s prostředkem jeden BMP. Prostředek .bmp generováno do adresáře, který je relativní vzhledem k kořenový adresář projektu.  
  
```  
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
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](https://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)
