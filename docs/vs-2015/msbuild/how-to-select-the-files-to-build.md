---
title: 'Postupy: Výběr souborů pro sestavení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, including files
- Include attribute [MSBuild]
ms.assetid: f5ff182f-7b3a-46fb-9335-37df54cfb8eb
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0968dd8914b99e8d47ef1364231059175aaf73fe
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63437906"
---
# <a name="how-to-select-the-files-to-build"></a>Postupy: Výběr souborů k sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při vytváření projektu, který obsahuje několik souborů, můžete vytvořit seznam každý soubor samostatně v souboru projektu nebo k zahrnutí všech souborů v jednom adresáři nebo vnořenou sadu adresáře můžete použít zástupné znaky.  
  
## <a name="specifying-inputs"></a>Určení vstupů  
 Položky představují vstup pro sestavení. Další informace o položky, naleznete v tématu [položky](../msbuild/msbuild-items.md).  
  
 Chcete-li zahrnout soubory pro sestavení, musí být obsažena v seznamu položek v [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] souboru projektu. Více souborů je přidat do seznamů položek včetně soubory jednotlivě nebo použití zástupných znaků zahrnout více souborů najednou.  
  
#### <a name="to-declare-items-individually"></a>Chcete-li deklarovat položky jednotlivě  
  
- Použití `Include` atributy podobně jako následující:  
  
     `<CSFile Include="form1.cs"/>`  
  
     – nebo –  
  
     `<VBFile Include="form1.vb"/>`  
  
    > [!NOTE]
    > Pokud se položky v kolekci položek nejsou ve stejném adresáři jako soubor projektu, musíte zadat úplnou nebo relativní cesta k položce. Například: `Include="..\..\form2.cs"`.  
  
#### <a name="to-declare-multiple-items"></a>Chcete-li deklarovat více položek  
  
- Použití `Include` atributy podobně jako následující:  
  
     `<CSFile Include="form1.cs;form2.cs"/>`  
  
     – nebo –  
  
     `<VBFile Include="form1.vb;form2.vb"/>`  
  
## <a name="specifying-inputs-with-wildcards"></a>Určení vstupů se zástupnými znaky  
 Můžete také použít zástupné znaky rekurzivně zahrnout všechny soubory nebo pouze konkrétní soubory z podadresáře jako vstupy pro sestavení. Další informace o zástupných znacích naleznete v tématu [položky](../msbuild/msbuild-items.md)  
  
 Následující příklady jsou založené na projekt, který obsahuje soubory grafiky v následujících adresářů a podadresářů, se nachází v adresáři projektu soubor projektu:  
  
 Project\Images\BestJpgs  
  
 Project\Images\ImgJpgs  
  
 Project\Images\ImgJpgs\Img1  
  
#### <a name="to-include-all-jpg-files-in-the-images-directory-and-subdirectories"></a>Zahrnout všechny soubory .jpg Imagí adresáře a podadresáře  
  
- Pomocí následujících `Include` atribut:  
  
     `Include="Images\**\*.jpg"`  
  
#### <a name="to-include-all-jpg-files-starting-with-img"></a>Chcete-li zahrnout všechny soubory .jpg počínaje "img"  
  
- Pomocí následujících `Include` atribut:  
  
     `Include="Images\**\img*.jpg"`  
  
#### <a name="to-include-all-files-in-directories-with-names-ending-in-jpgs"></a>Chcete-li zahrnout všechny soubory v adresářích s názvy končící na "formátu JPG využívá"  
  
- Použijte jednu z následujících `Include` atributy:  
  
     `Include="Images\**\*jpgs\*.*"`  
  
     – nebo –  
  
     `Include="Images\**\*jpgs\*"`  
  
## <a name="passing-items-to-a-task"></a>Předávání položky k úkolu  
 V souboru projektu, můžete použít @ zápis () v úlohách k určení celé položky seznamu jako vstup pro sestavení. Tento typ notation můžete použít, ať už samostatně seznam všech souborů, nebo použít zástupné znaky.  
  
#### <a name="to-use-all-visual-c-or-visual-basic-files-as-inputs"></a>Použití všech Visual C# nebo Visual Basic souborů jako vstupy  
  
- Použití `Include` atributy podobný následujícímu:  
  
     `<CSC Sources="@(CSFile)">...</CSC>`  
  
     – nebo –  
  
     `<VBC Sources="@(VBFile)">...</VBC>`  
  
> [!NOTE]
> Je nutné použít zástupné znaky se položky, které chcete určit vstupy pro sestavení; Nelze zadat vstupy pomocí `Sources` atribut [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] úkoly, jako [Csc](../msbuild/csc-task.md) nebo [Vbc –](../msbuild/vbc-task.md). V následujícím příkladu není platný v souboru projektu:  
>   
> `<CSC Sources="*.cs">...</CSC>`  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje projekt, který obsahuje všechny vstupní soubory samostatně.  
  
```  
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
 Následující příklad kódu používá k zahrnutí všech souborů .cs zástupný znak.  
  
```  
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
 [Postupy: Vyloučení souborů ze sestavení](../msbuild/how-to-exclude-files-from-the-build.md)   
 [Položky](../msbuild/msbuild-items.md)
