---
title: "Postupy: Vyberte soubory k sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, including files
- Include attribute [MSBuild]
ms.assetid: f5ff182f-7b3a-46fb-9335-37df54cfb8eb
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: d5e6e13dc9700269f42d8ed640ea725cef9d6b05
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-select-the-files-to-build"></a>Postupy: Výběr souborů pro sestavení
Při sestavování projektu obsahující několik souborů, můžete vytvořit seznam každý soubor v souboru projektu samostatně nebo můžete zahrnout všechny soubory v jednom adresáři nebo sadu adresáře vnořené zástupné znaky.  
  
## <a name="specifying-inputs"></a>Určení vstupy  
 Položky představují vstupy pro sestavení. Další informace o položek najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
 Chcete-li zahrnout soubory pro sestavení, musí být zahrnuty v seznamu položek v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. Více souborů lze přidat do položky seznamů včetně souborů jednotlivě nebo pomocí zástupných znaků najednou zahrnout mnoho souborů.  
  
#### <a name="to-declare-items-individually"></a>Chcete-li deklarovat položky jednotlivě  
  
-   Použití `Include` atributy, které jsou podobné pro následující:  
  
     `<CSFile Include="form1.cs"/>`  
  
     - nebo –  
  
     `<VBFile Include="form1.vb"/>`  
  
    > [!NOTE]
    >  Pokud položky v kolekci položky nejsou ve stejném adresáři jako soubor projektu, musíte zadat úplná nebo relativní cestu k položce. Příklad: `Include="..\..\form2.cs"`.  
  
#### <a name="to-declare-multiple-items"></a>Chcete-li deklarovat více položek  
  
-   Použití `Include` atributy, které jsou podobné pro následující:  
  
     `<CSFile Include="form1.cs;form2.cs"/>`  
  
     - nebo –  
  
     `<VBFile Include="form1.vb;form2.vb"/>`  
  
## <a name="specifying-inputs-with-wildcards"></a>Zadání vstupy se zástupnými znaky  
 Můžete také použít zástupné znaky k rekurzivnímu zahrnovat všechny soubory nebo pouze konkrétní soubory z podadresáře jako vstupy pro sestavení. Další informace o zástupné znaky, najdete v části [položky](../msbuild/msbuild-items.md)  
  
 Následující příklady jsou založeny na projekt, který obsahuje soubory v následujících adresářů a vytvoří se podadresáře, do souboru projektu, který je umístěný v adresáři projektu:  
  
 Project\Images\BestJpgs  
  
 Project\Images\ImgJpgs  
  
 Project\Images\ImgJpgs\Img1  
  
#### <a name="to-include-all-jpg-files-in-the-images-directory-and-subdirectories"></a>Zahrnout všechny soubory .jpg v adresáři bitové kopie a podadresáře  
  
-   Použijte následující `Include` atribut:  
  
     `Include="Images\**\*.jpg"`  
  
#### <a name="to-include-all-jpg-files-starting-with-img"></a>Zahrnout všechny soubory .jpg počínaje "img"  
  
-   Použijte následující `Include` atribut:  
  
     `Include="Images\**\img*.jpg"`  
  
#### <a name="to-include-all-files-in-directories-with-names-ending-in-jpgs"></a>Zahrnout všechny soubory v adresářích s názvy, které končí na "formátu JPG využívá"  
  
-   Použijte jednu z následujících `Include` atributy:  
  
     `Include="Images\**\*jpgs\*.*"`  
  
     - nebo –  
  
     `Include="Images\**\*jpgs\*"`  
  
## <a name="passing-items-to-a-task"></a>Předávání položky úkolů  
 V souboru projektu, můžete použít @ () zápis v úlohách k určení celou položku seznamu jako vstup pro sestavení. Můžete použít tento zápis, zda seznam všech souborů samostatně nebo použít zástupné znaky.  
  
#### <a name="to-use-all-visual-c-or-visual-basic-files-as-inputs"></a>Chcete použít jako vstupy soubory všechny Visual C# nebo Visual Basic  
  
-   Použití `Include` atributy podobný následujícímu:  
  
     `<CSC Sources="@(CSFile)">...</CSC>`  
  
     - nebo –  
  
     `<VBC Sources="@(VBFile)">...</VBC>`  
  
> [!NOTE]
>  Je nutné použít zástupné znaky se položky zadejte vstupy pro sestavení; Nelze zadat vstupy pomocí `Sources` atribut [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy jako například [Csc](../msbuild/csc-task.md) nebo [Vbc –](../msbuild/vbc-task.md). V souboru projektu není platný v následujícím příkladu:  
>   
>  `<CSC Sources="*.cs">...</CSC>`  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje projekt, který zahrnuje všechny vstupní soubory samostatně.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Builtdir>built</Builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="Form1.cs"/>  
        <CSFile Include="AssemblyInfo.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu používá zástupný znak zahrnout všechny soubory .cs.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vyloučení souborů ze sestavení](../msbuild/how-to-exclude-files-from-the-build.md)   
 [Položky](../msbuild/msbuild-items.md)