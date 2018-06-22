---
title: 'Postupy: odkazování na název nebo umístění souboru projektu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21077b9533a0f7e4490c5b12a3571b3f2d001219
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302806"
---
# <a name="how-to-reference-the-name-or-location-of-the-project-file"></a>Postupy: Odkazování na název nebo umístění souboru projektu
Můžete použít název nebo umístění projektu v souboru projektu bez nutnosti vytvářet vlastní vlastnosti. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje rezervované vlastnosti, které odkazují na název souboru projektu a další vlastnosti související s projektem. Další informace o rezervované vlastnosti najdete v tématu [MSBuild vyhrazené a známé vlastnosti](../msbuild/msbuild-reserved-and-well-known-properties.md).  
  
## <a name="using-the-project-properties"></a>Pomocí vlastností projektu
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje některé rezervované vlastnosti, které můžete použít bez definování je pokaždé, když v souborech projektu. Například vlastnost vyhrazené `MSBuildProjectName` poskytuje odkaz na název souboru projektu. Vlastnost vyhrazené `MSBuildProjectDirectory` poskytuje odkaz na umístění souboru projektu.
  
#### <a name="to-use-the-project-properties"></a>Použití vlastností projektu
  
-   Odkazovat na vlastnost v souboru projektu pomocí notace $ (), stejně jako s jakoukoli vlastnost. Příklad:  
  
    ```xml  
    <CSC Sources = "@(CSFile)"   
        OutputAssembly = "$(MSBuildProjectName).exe"/>  
    </CSC>  
    ```          
  
 Výhodou používání rezervované vlastnosti je, že jsou automaticky součástí změny k názvu souboru projektu. Při příštím sestavení projektu, výstupní soubor bude mít nový název se žádná další akce požadované z vaší strany.  
  
> [!NOTE]
>  Rezervované vlastnosti nelze jej předefinovat v souboru projektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad souboru projekt odkazuje na název projektu jako rezervované vlastnosti a zadejte název pro výstup.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"   
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

## <a name="example"></a>Příklad
 Následující příklad souboru projektu používá `MSBuildProjectDirectory` vyhrazené vlastnost vytvořit úplná cesta k souboru v umístění souboru projektu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">     
    
    <!-- Build the path to a file in the root of the project -->  
    <PropertyGroup>  
        <NewFilePath>$([System.IO.Path]::Combine($(MSBuildProjectDirectory), `BuildInfo.txt`))</NewFilePath>
    </PropertyGroup>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
[MSBuild](../msbuild/msbuild.md)  
 [Vyhrazené a známé vlastnosti nástroje MSBuild](../msbuild/msbuild-reserved-and-well-known-properties.md)
