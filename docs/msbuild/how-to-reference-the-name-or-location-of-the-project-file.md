---
title: "Postupy: odkazování na název nebo umístění souboru projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locations, referencing
- locations
- MSBuildProjectName property
- MSBuild, referencing the project file
- names, referencing
- reserved properties
- project files, referencing
ms.assetid: c8fcc594-5d37-4e2e-b070-4d9c012043b5
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7a688473b4657d905397d4798451b4860578ef0d
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-reference-the-name-or-location-of-the-project-file"></a>Postupy: Odkazování na název nebo umístění souboru projektu
Můžete použít název nebo umístění projektu v souboru projektu bez nutnosti vytvářet vlastní vlastnosti. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]poskytuje rezervované vlastnosti, které odkazují na název souboru projektu a další vlastnosti související s projektem. Další informace o rezervované vlastnosti najdete v tématu [MSBuild vyhrazené a známé vlastnosti](../msbuild/msbuild-reserved-and-well-known-properties.md).  
  
## <a name="using-the-msbuildprojectname-property"></a>Pomocí MSBuildProjectName – vlastnost  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje některé rezervované vlastnosti, které můžete použít bez definování je pokaždé, když v souborech projektu. Například vlastnost vyhrazené `MSBuildProjectName` poskytuje odkaz na název souboru projektu.  
  
#### <a name="to-use-the-msbuildprojectname-property"></a>Použít MSBuildProjectName – vlastnost  
  
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
[MSBuild](../msbuild/msbuild.md)  
 [Vyhrazené a známé vlastnosti nástroje MSBuild](../msbuild/msbuild-reserved-and-well-known-properties.md)