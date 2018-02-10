---
title: "Postupy: použití stejného cíle ve více souborech projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, importing
- MSBuild, using the same target in multiple project files
ms.assetid: 163734bd-1bfd-4093-a730-7741fc21742d
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: be56829881865887eb07810d2545ee1ed965ab3a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-use-the-same-target-in-multiple-project-files"></a>Postupy: Použití stejného cíle ve více souborech projektu
Pokud jste vytvořili několik [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory projektu, vám může zjistit, budete muset použít stejné úlohy a cíle v souborech jiný projekt. Místo v každém projektu souboru, včetně úplný popis těchto úloh nebo cíle, můžete uložit do samostatného souboru cíl a poté importovat do jiné projekt, který potřebuje používat cíl daného projektu.  
  
## <a name="using-the-import-element"></a>Pomocí Import – Element  
 `Import` Element slouží k vložení jednoho souboru projektu do jiného souboru projektu. Soubor projektu, která se importují musí být platná [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu a obsahuje kód XML ve správném formátu. `Project` Atribut určuje cestu k souboru importované projektu. Další informace o `Import` elementu, najdete v části [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md).  
  
#### <a name="to-import-a-project"></a>Import projektu  
  
1.  Definujte v import souboru projektu, všechny vlastnosti a položky, které se používají jako parametry pro vlastnosti a položky v importovaných projektu.  
  
2.  Použití `Import` elementu, který chcete importovat projekt. Příklad:  
  
     `<Import Project="MyCommon.targets"/>`  
  
3.  Následující `Import` elementu, definujte všechny vlastnosti a položky, které musí přepsat výchozí definice vlastností a položek v importovaných projektu.  
  
## <a name="order-of-evaluation"></a>Pořadí vyhodnocení  
 Když [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dosáhne `Import` elementu, importovaný projekt efektivně vložený do Import projektu na umístění `Import` elementu. Proto umístění `Import` element může mít vliv na hodnoty vlastností a položek. Je důležité si uvědomit, vlastnosti a položky, které jsou nastaveny sadou importované projektu a vlastnosti a položky používané importované projektu.  
  
 Při sestavení projektu všechny vlastnosti se vyhodnocují jako první, za nímž následuje položky. Například následující kód XML definuje importovaný soubor projektu MyCommon.targets:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Name>MyCommon</Name>  
    </PropertyGroup>  
  
    <Target Name="Go">  
        <Message Text="Name=$(Name)"/>  
    </Target>  
</Project>  
```  
  
 Následující kód XML definuje MyApp.proj, který importuje MyCommon.targets:  
  
```xml  
<Project  
    DefaultTargets="Go"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Name>MyApp</Name>  
    </PropertyGroup>  
    <Import Project="MyCommon.targets"/>  
</Project>  
```  
  
 Při sestavení projektu, se zobrazí následující zprávu:  
  
 `Name="MyCommon"`  
  
 Protože je po vlastnost Importovat projekt `Name` byla definována v MyApp.proj, definice `Name` MyCommon.targets přepsání definici v MyApp.proj. Pokud projekt importu před vlastnost, kterou je definován název sestavení by zobrazí se následující zpráva:  
  
 `Name="MyApp"`  
  
#### <a name="use-the-following-approach-when-importing-projects"></a>Použijte následující postup při importu projekty  
  
1.  Definování v souboru projektu, všechny vlastnosti a položky, které se používají jako parametry pro vlastnosti a položky v importovaných projektu.  
  
2.  Importujte projekt.  
  
3.  V souboru projektu definujte všechny vlastnosti a položky, které musí přepsat výchozí definice vlastností a položek v importovaných projektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje soubor MyCommon.targets, který importuje druhém příkladu kódu. Souboru .targets vyhodnotí vlastnosti z Import konfigurace sestavení projektu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Flavor Condition="'$(Flavor)'==''">DEBUG</Flavor>  
        <Optimize Condition="'$(Flavor)'=='RETAIL'">yes</Optimize>  
        <appname>$(MSBuildProjectName)</appname>  
    <PropertyGroup>  
    <Target Name="Build">  
        <Csc Sources="hello.cs"  
            Optimize="$(Optimize)"  
            OutputAssembly="$(appname).exe"/>  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu importuje soubor MyCommon.targets.  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Flavor>RETAIL</Flavor>  
    </PropertyGroup>  
    <Import Project="MyCommon.targets"/>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md)   
 [Cíle](../msbuild/msbuild-targets.md)