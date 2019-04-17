---
title: 'Postupy: Odkazování na název nebo umístění souboru projektu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- locations, referencing
- locations
- MSBuildProjectName property
- MSBuild, referencing the project file
- names, referencing
- reserved properties
- project files, referencing
ms.assetid: c8fcc594-5d37-4e2e-b070-4d9c012043b5
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6e9493050e5deb2e25cf526d2464214399b10a7c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670365"
---
# <a name="how-to-reference-the-name-or-location-of-the-project-file"></a>Postupy: Odkazy na název nebo umístění souboru projektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Název nebo umístění projektu můžete použít v souboru projektu bez nutnosti vytvářet vlastní vlastnosti. [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] poskytuje rezervované vlastnosti, které odkazují na název souboru projektu a další vlastnosti související s projektem. Další informace o rezervované vlastnosti najdete v tématu [MSBuild vyhrazené a známé vlastnosti](../msbuild/msbuild-reserved-and-well-known-properties.md).  
  
## <a name="using-the-msbuildprojectname-property"></a>MSBuildProjectName – vlastnost  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] poskytuje některé rezervované vlastnosti, které můžete použít bez jejich definováním pokaždé, když v souborech projektu. Například vlastnost vyhrazené `MSBuildProjectName` poskytuje odkaz na název souboru projektu.  
  
#### <a name="to-use-the-msbuildprojectname-property"></a>Chcete-li použít MSBuildProjectName – vlastnost  
  
- Odkazovat na vlastnost v souboru projektu se zápis $ (), stejně jako s jakoukoli vlastnost. Příklad:  
  
  ```  
  <CSC Sources = "@(CSFile)"   
      OutputAssembly = "$(MSBuildProjectName).exe"/>  
  </CSC>  
  ```  
  
  Výhodou použití rezervované vlastnosti je, že jsou automaticky součástí žádné změny k názvu souboru projektu. Při příštím sestavení projektu, výstupní soubor bude mít nový název se vyžadovat z vaší strany žádná další akce.  
  
> [!NOTE]
>  Rezervované vlastnosti nelze předefinovat v souboru projektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad souboru projektu odkazuje na název projektu jako vyhrazené vlastnosti a určit název pro výstup.  
  
```  
<Project xmlns="http://scheams.microsoft.com/developer/msbuild/2003"   
    DefaultTargets = "Compile">  
  
    <!-- Specify the inputs -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using  
        input files of type CSFile -->  
        <CSC Sources = "@(CSFile)"  
            OutputAssembly = "$(MSBuildProjectName).exe" >  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the project -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
[MSBuild](msbuild.md)  
 [Vyhrazené a známé vlastnosti nástroje MSBuild](../msbuild/msbuild-reserved-and-well-known-properties.md)
