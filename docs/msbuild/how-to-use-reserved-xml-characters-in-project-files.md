---
title: "Postupy: použití vyhrazených znaků XML v souborech projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, using reserved XML characters
- MSBuild, reserved XML characters
ms.assetid: 1ae37275-96bf-4e6e-897b-6b048e5bbe93
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: c477cd9160a765a554cfa432b023b20eb6ef6b4e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-reserved-xml-characters-in-project-files"></a>Postupy: Použití vyhrazených znaků XML v souborech projektu
Při vytváření soubory projektu, musíte může používat vyhrazené znaky jazyka XML, například v hodnotách vlastnosti nebo ve hodnoty parametrů úloh. Ale některé vyhrazené znaky musí nahradit odpovídajícími pojmenované entit, tak, aby soubor projektu lze analyzovat.  
  
## <a name="using-reserved-characters"></a>Pomocí vyhrazené znaky  
 Následující tabulka popisuje vyhrazené znaky jazyka XML, které se musí nahradit odpovídajícími odpovídající entita s názvem, aby soubor projektu lze analyzovat.  
  
|Vyhrazený znak|Pojmenované entity|  
|------------------------|------------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|"|&quot;|  
|'|&apos;|  
  
#### <a name="to-use-double-quotes-in-a-project-file"></a>Použití dvojité uvozovky v souboru projektu  
  
-   Nahraďte odpovídající s názvem entity, dvojité uvozovky &quot;. Například umístit dvojité uvozovky kolem `EXEFile` seznamu položek, zadejte:  
  
    ```xml  
    <Message Text="The output file is "@(EXEFile)"."/>  
    ```  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu kódu používají dvojité uvozovky zvýrazněte název souboru ve zprávě, která je výstupní soubor projektu.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>"HelloWorldCS"</appname>  
    </PropertyGroup>  
    <!-- Specify the inputs -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs" />  
    </ItemGroup>  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input  
        files of type CSFile -->  
        <Csc Sources = "@(CSFile)">  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile"/>  
        </Csc>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is "@(EXEFile)"."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md) [nástroje MSBuild](../msbuild/msbuild.md)