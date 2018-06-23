---
title: 'Postupy: sestavení stejných zdrojových souborů s různými možnostmi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- source files, building with different options
- MSBuild, properties
- project properties, modifying
- Hello World example [Visual Studio]
ms.assetid: d14f1212-ddd9-434f-b138-f840011b0fb2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f08a159d9490c5c8f92c5b093bc1b52d01c3b3d
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326202"
---
# <a name="how-to-build-the-same-source-files-with-different-options"></a>Postupy: Sestavení stejných zdrojových souborů s různými možnostmi
Při sestavování projektů zkompilujete často stejné komponenty s možnostmi jiné sestavení. Můžete například vytvořit sestavení ladicí verze informací o symbolu nebo sestavení pro vydání s bez informací o symbolu, ale s povolenými optimalizacemi. Nebo můžete vytvořit projekt ke spuštění na konkrétní platformu, jako je například x86 nebo [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)]. V těchto případech většina možností sestavení zůstat stejné. změnily se jenom pár možností k řízení je konfigurace sestavení. S [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], použijte vlastnosti a podmínky k vytvoření konfigurace jiné sestavení.  
  
## <a name="using-properties-to-modify-projects"></a>Pomocí vlastností k úpravě projekty  
 `Property` Element definuje proměnnou, kterou je odkazováno v souboru projektu, jako je například umístění dočasný adresář, nebo můžete nastavit hodnoty pro vlastnosti, které se používají v několika konfigurace, například sestavení ladicí verze a verze sestavení. Další informace o vlastnostech najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
 Vlastnosti můžete změnit konfiguraci vašeho sestavení bez nutnosti změny souboru projektu. `Condition` Atribut `Property` elementu a `PropertyGroup` element vám umožní změnit hodnotu vlastnosti. Další informace o [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podmínky, najdete v části [podmínky](../msbuild/msbuild-conditions.md).  
  
#### <a name="to-set-a-group-of-properties-based-on-another-property"></a>Nastavit skupinu vlastností na základě jiné vlastnosti  
  
-   Použití `Condition` atribut `PropertyGroup` element podobný následujícímu:  
  
    ```xml  
    <PropertyGroup Condition="'$(Flavor)'=='DEBUG'">  
        <DebugType>full</DebugType>  
        <Optimize>no</Optimize>  
    </PropertyGroup>  
    ```  
  
#### <a name="to-define-a-property-based-on-another-property"></a>K definování vlastností na základě jiné vlastnosti  
  
-   Použití `Condition` atribut `Property` element podobný následujícímu:  
  
    ```xml  
    <DebugType Condition="'$(Flavor)'=='DEBUG'">full</DebugType>  
    ```  
  
## <a name="specifying-properties-on-the-command-line"></a>Zadání vlastnosti příkazového řádku  
 Jakmile souboru projektu je zapsán do přijmout více konfigurací, musíte mít možnost změnit tyto konfigurace vždy, když vytvoříte projekt. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje možnost tím, že vlastnosti ho zadat na příkazovém řádku pomocí **/property** nebo **/p** přepínače.  
  
#### <a name="to-set-a-project-property-at-the-command-line"></a>Chcete-li nastavit vlastnost projektu na příkazovém řádku  
  
-   Použití **/property** přepínač s vlastností a hodnotu vlastnosti. Příklad:  
  
    ```cmd  
    msbuild file.proj /property:Flavor=Debug  
    ```  
  
     - nebo –  
  
    ```cmd  
    Msbuild file.proj /p:Flavor=Debug  
    ```  
  
#### <a name="to-specify-more-than-one-project-property-at-the-command-line"></a>Chcete-li zadat více než jednu vlastnost projektu na příkazovém řádku  
  
-   Použít **/property** nebo **/p** přepínač vícekrát s vlastností a hodnoty vlastností, nebo využít **/property** nebo **/p** přepínače a více vlastností oddělujte středníkem (;). Příklad:  
  
    ```cmd  
    msbuild file.proj /p:Flavor=Debug;Platform=x86  
    ```  
  
     - nebo –  
  
    ```cmd  
    msbuild file.proj /p:Flavor=Debug /p:Platform=x86  
    ```  
  
 Proměnné prostředí jsou považovány také jako vlastnosti a jsou automaticky součástí podle [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Další informace o použití proměnných prostředí najdete v tématu [postupy: použití proměnných prostředí v sestavení](../msbuild/how-to-use-environment-variables-in-a-build.md).  
  
 Hodnotu vlastnosti, která je zadána na příkazovém řádku mají přednost před jakoukoli hodnotu, která je nastavena pro stejnou vlastnost v souboru projektu, a hodnota v souboru projektu má přednost před hodnotu v proměnné prostředí.  
  
 Toto chování můžete změnit pomocí `TreatAsLocalProperty` atribut ve značce projektu. Pro názvy vlastností, které jsou uvedeny se tento atribut hodnota vlastnosti, která je zadána na příkazovém řádku nemá přednost hodnota v souboru projektu. Příklad najdete dále v tomto tématu.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu projektu "Hello World" obsahuje dvě nové skupiny vlastnosti, které lze použít k vytvoření sestavení ladicí verze a sestavení pro vydání.  
  
 Chcete-li sestavení ladicí verze tohoto projektu, zadejte:  
  
```cmd  
msbuild consolehwcs1.proj /p:flavor=debug  
```  
  
 Chcete-li vytvořit maloobchodní verze tohoto projektu, zadejte:  
  
```cmd  
msbuild consolehwcs1.proj /p:flavor=retail  
```  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <!-- Sets the default flavor of an environment variable called   
    Flavor is not set or specified on the command line -->  
    <PropertyGroup>  
        <Flavor Condition="'$(Flavor)'==''">DEBUG</Flavor>  
    </PropertyGroup>  
  
    <!-- Define the DEBUG settings -->  
    <PropertyGroup Condition="'$(Flavor)'=='DEBUG'">  
        <DebugType>full</DebugType>  
        <Optimize>no</Optimize>  
    </PropertyGroup>  
  
    <!-- Define the RETAIL settings -->  
    <PropertyGroup Condition="'$(Flavor)'=='RETAIL'">  
        <DebugType>pdbonly</DebugType>  
        <Optimize>yes</Optimize>  
    </PropertyGroup>  
  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>HelloWorldCS</appname>  
    </PropertyGroup>  
  
    <!-- Specify the inputs by type and file name -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input files  
        of type CSFile -->  
        <CSC  Sources = "@(CSFile)"  
            DebugType="$(DebugType)"  
            Optimize="$(Optimize)"  
            OutputAssembly="$(appname).exe" >  
  
            <!-- Set the OutputAssembly attribute of the CSC  
            task to the name of the executable file that is   
            created -->  
            <Output TaskParameter="OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `TreatAsLocalProperty` atribut. `Color` Vlastnost má hodnotu `Blue` v souboru projektu a `Green` v příkazovém řádku. S `TreatAsLocalProperty="Color"` ve značce projektu vlastnost příkazového řádku (`Green`) není přepsat vlastnost, která je definována v souboru projektu (`Blue`).  
  
 Pokud chcete vytvořit projekt, zadejte následující příkaz:  
  
```cmd  
msbuild colortest.proj /t:go /property:Color=Green  
```  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
ToolsVersion="4.0" TreatAsLocalProperty="Color">  
  
    <PropertyGroup>  
        <Color>Blue</Color>  
    </PropertyGroup>  
  
    <Target Name="go">  
        <Message Text="Color: $(Color)" />  
    </Target>  
</Project>  
  
<!--  
  Output with TreatAsLocalProperty="Color" in project tag:  
     Color: Blue  
  
  Output without TreatAsLocalProperty="Color" in project tag:  
     Color: Green  
-->  
```  
  
## <a name="see-also"></a>Viz také  
[MSBuild](../msbuild/msbuild.md)  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Project – element (MSBuild)](../msbuild/project-element-msbuild.md)