---
title: 'Postupy: vyloučení souborů ze sestavení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, excluding files
- wildcards, MSBuild
ms.assetid: 1be36e45-01da-451c-972d-f9fc0e7d663c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb8e8ba51f4aaeed0242147d46fd282b95452d91
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-exclude-files-from-the-build"></a>Postupy: Vyloučení souborů ze sestavení
V souboru projektu slouží jako vstupy pro sestavení zahrnout všechny soubory v jednom adresáři nebo sadu adresáře vnořené zástupné znaky. Však může být jeden soubor v adresáři nebo v adresáři ve vnořených sadu adresáře, které nechcete zahrnout jako vstup pro sestavení. Tento soubor nebo adresář můžete výslovně vyloučit ze seznamu vstupy. V projektu, který chcete zahrnout za určitých podmínek může být také soubor. Je možné deklarovat explicitně podmínky, za kterých je soubor součástí sestavení.  
  
## <a name="excluding-a-file-or-directory-from-the-inputs-for-a-build"></a>S výjimkou souboru nebo adresáři ze vstupních údajů pro sestavení  
 Položka seznamy jsou vstupní soubory pro sestavení. Položky, které chcete zahrnout jsou deklarovány samostatně nebo jako skupinu pomocí `Include` atribut. Příklad:  
  
```xml  
<CSFile Include="Form1.cs"/>  
<CSFile Include ="File1.cs;File2.cs"/>  
<CSFile Include="*.cs"/>  
<JPGFile Include="Images\**\*.jpg"/>  
```  
  
 Pokud jste použili zástupné znaky jako vstupy pro sestavení zahrnout všechny soubory jednoho adresáře nebo sadu vnořené adresářů, může být jeden nebo více souborů v adresáři nebo v adresáři v sadu vnořené adresáře, které nechcete zahrnout. Chcete-li vyloučit položku ze seznamu položek, použijte `Exclude` atribut.  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2"></a>Zahrnout všechny soubory kromě Form2 cs nebo VB  
  
-   Použijte jednu z následujících `Include` a `Exclude` atributy:  
  
    ```xml  
    <CSFile Include="*.cs" Exclude="Form2.cs"/>  
    ```  
  
     - nebo –  
  
    ```xml  
    <VBFile Include="*.vb" Exclude="Form2.vb"/>  
    ```  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2-and-form3"></a>Zahrnout všechny soubory s výjimkou Form2 a Form3 cs nebo VB  
  
-   Použijte jednu z následujících `Include` a `Exclude` atributy:  
  
    ```xml  
    <CSFile Include="*.cs" Exclude="Form2.cs;Form3.cs"/>  
    ```  
  
     - nebo –  
  
    ```xml  
    <VBFile Include="*.vb" Exclude="Form2.vb;Form3.vb"/>  
    ```  
  
#### <a name="to-include-all-jpg-files-in-subdirectories-of-the-images-directory-except-those-in-the-version2-directory"></a>Zahrnout všechny soubory .jpg v podadresářích adresáře bitové kopie, s výjimkou těch v adresáři Version2  
  
-   Použijte následující `Include` a `Exclude` atributy:  
  
    ```xml  
    <JPGFile  
        Include="Images\**\*.jpg"  
        Exclude = "Images\**\Version2\*.jpg"/>  
    ```  
  
    > [!NOTE]
    >  Musíte zadat cestu pro oba atributy. Pokud se absolutní cesta používá k určení umístění souboru v `Include` atribut, musíte taky použít absolutní cesta ve `Exclude` atribut; je-li použít relativní cestu do `Include` atribut, musíte taky použít relativní cestu v `Exclude`atribut.  
  
## <a name="using-conditions-to-exclude-a-file-or-directory-from-the-inputs-for-a-build"></a>Pomocí podmínek pro vyloučení souboru nebo adresáři ze vstupních údajů pro sestavení  
 Pokud existují položky, které chcete zahrnout, například v sestavení ladicí verze, ale není sestavení pro vydání, můžete použít `Condition` atribut k určení podmínek, pod kterým chcete zahrnout položky.  
  
#### <a name="to-include-the-file-formulavb-only-in-release-builds"></a>Zahrnout soubor Formula.vb pouze v sestavení pro vydání  
  
-   Použití `Condition` atribut podobný následujícímu:  
  
    ```xml  
    <Compile  
        Include="Formula.vb"  
        Condition=" '$(Configuration)' == 'Release' " />  
    ```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu sestavení projektu se všemi .cs souborů v adresáři s výjimkou Form2.cs.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs Exclude="Form2.cs"/>  
  
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
 [Položky](../msbuild/msbuild-items.md)   
 [MSBuild](../msbuild/msbuild.md) [postup: Vyberte soubory k sestavení](../msbuild/how-to-select-the-files-to-build.md)