---
title: "Generování v procesu sestavení kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, build tasks
- text templates, transforming by using msbuild
ms.assetid: 4da43429-2a11-4d7e-b2e0-9e4af7033b5a
caps.latest.revision: "28"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: e26560740dd8d6f86d80dc5063a5c9b55cac8171
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="code-generation-in-a-build-process"></a>Vytvoření kódu v procesu sestavení
[Transformace textu](../modeling/code-generation-and-t4-text-templates.md) nelze vyvolat v rámci [proces sestavení](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692) z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení. Některé úlohy sestavení se specializují na transformaci textu. Úlohy sestavení T4 spouštějí textové šablony návrhu a rovněž kompilují textové šablony běhu (předzpracované).  
  
 V závislosti na tom, který stroj sestavení používáte, jsou určité rozdíly v tom, co úlohy sestavení mohou provádět. Při sestavování řešení v sadě Visual Studio textové šablony otevřete Visual Studio rozhraní API (EnvDTE), pokud [hostspecific = "true"](../modeling/t4-template-directive.md) nastavený atribut. Ale který nemá hodnotu true, když vytvoříte řešení z příkazového řádku nebo při zahájení sestavení serveru pomocí sady Visual Studio. V těchto případech provádí sestavení nástroj MSBuild a používá se jiný hostitel T4.  
  
 To znamená, že nelze přístup věcmi, jako jsou názvy souborů projektu stejným způsobem, když vytvoříte šablonu text v nástroji MSBuild. Můžete však [předání informací o prostředí do textové šablony a procesory direktiv pomocí parametrů sestavení](#parameters).  
  
##  <a name="buildserver"></a>Konfigurace vašich počítačů  
 Chcete-li úlohami sestavení ve svém vývojovém počítači, nainstalujte modelování SDK pro Visual Studio.
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

 Pokud [vašem serveru sestavení](http://msdn.microsoft.com/Library/788443c3-0547-452e-959c-4805573813a9) běží na počítači, na který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není nainstalovaný, zkopírujte následující soubory do počítače sestavení z vývojovém počítači. Nahraďte nejnovější číslo verze pro ' *'.  
  
-   $(ProgramFiles)\MSBuild\Microsoft\VisualStudio\v*.0\TextTemplating  
  
    -   Microsoft.VisualStudio.TextTemplating.Sdk.Host.*.0.dll  
  
    -   Microsoft.TextTemplating.Build.Tasks.dll  
  
    -   Microsoft.TextTemplating.targets  
  
-   $(ProgramFiles) \Microsoft Visual Studio *.0\VSSDK\VisualStudioIntegration\Common\Assemblies\v4.0  
  
    -   Microsoft.VisualStudio.TextTemplating.*.0.dll  
  
    -   Microsoft.VisualStudio.TextTemplating.Interfaces.*.0.dll (několik souborů)  
  
    -   Microsoft.VisualStudio.TextTemplating.VSHost.*.0.dll  
  
-   $(ProgramFiles) \Microsoft Visual Studio *.0\Common7\IDE\PublicAssemblies\  
  
    -   Microsoft.VisualStudio.TextTemplating.Modeling.*.0.dll  
  
## <a name="to-edit-the-project-file"></a>Úprava souboru projektu  
 Budete muset upravit soubor projektu do některé z funkcí konfigurace v nástroji MSBuild.  
  
 V Průzkumníku řešení, zvolte **uvolnění** z místní nabídky projektu. Tím umožníte úpravu souborů .csproj nebo .vbproj v editoru XML.  
  
 Po dokončení úprav, vyberte **opětovného načtení**.  
  
## <a name="import-the-text-transformation-targets"></a>Import cílů transformace textu  
 V souboru .vbproj nebo .csproj vyhledejte řádek podobný následujícímu:  
  
 `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`  
  
 \-nebo –  
  
 `<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`  
  
 Za tento řádek vložte import šablonování textu:  
  
```xml  
<!-- Optionally make the import portable across VS versions -->  
  <PropertyGroup>  
    <!-- Get the Visual Studio version - defaults to 10: -->  
    <VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">10.0</VisualStudioVersion>  
    <!-- Keep the next element all on one line: -->  
    <VSToolsPath Condition="'$(VSToolsPath)' == ''">$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)</VSToolsPath>  
  </PropertyGroup>  
  
<!-- This is the important line: -->  
  <Import Project="$(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets" />  
```  
  
## <a name="transforming-templates-in-a-build"></a>Transformace šablon v sestavení  
 Do souboru projektu lze vložit některé vlastnosti, které slouží k řízení úlohy transformace:  
  
-   Spuštění úlohy transformace na začátku každého sestavení:  
  
    ```xml  
    <PropertyGroup>  
        <TransformOnBuild>true</TransformOnBuild>  
    </PropertyGroup>  
    ```  
  
-   Přepsání souborů, které jsou určeny jen pro čtení, protože například nejsou rezervovány:  
  
    ```xml  
    <PropertyGroup>  
        <OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOutputFiles>  
    </PropertyGroup>  
    ```  
  
-   Transformace všech šablon při každém spuštění:  
  
    ```xml  
    <PropertyGroup>  
        <TransformOutOfDateOnly>false</TransformOutOfDateOnly>  
    </PropertyGroup>  
    ```  
  
     Ve výchozím nastavení úloha T4 nástroje MSBuild znovu vygeneruje výstupní soubor, pokud je starší než její soubory šablony, nebo všechny vložené soubory, nebo všechny soubory, které byly předtím čteny šablonou nebo procesorem direktiv, který používá. Jedná se o mnohem komplexnější test závislostí, než jaký používá příkaz Transformovat všechny šablony v sadě Visual Studio, který pouze porovnává datum šablony a výstupního souboru.  
  
 Pokud chcete v projektu provést pouze transformace textu, vyvolejte úlohu TransformAll:  
  
 `msbuild myProject.csproj /t:TransformAll`  
  
 Transformace konkrétní textové šablony:  
  
 `msbuild myProject.csproj /t:Transform /p:TransformFile="Template1.tt"`  
  
 U příkazu TransformFile lze použít zástupné znaky:  
  
 `msbuild dsl.csproj /t:Transform /p:TransformFile="GeneratedCode\**\*.tt"`  
  
## <a name="source-control"></a>Správa zdrojového kódu  
 Systém správy zdrojového kódu není nijak integrován. Můžete však přidat vlastní rozšíření, například pro rezervaci a vrácení vygenerovaného souboru. Úloha transformace textu ve výchozím nastavení zabraňuje přepsání souboru, který je určený jen pro čtení, a když na takový soubor narazí, bude do seznamu chyb sady Visual Studio zaprotokolována chyba a tato úloha selže.  
  
 Pokud chcete určit, že se soubory určené jen pro čtení mají přepisovat, vložte tuto vlastnost:  
  
 `<OverwriteReadOnlyOuputFiles>true</OverwriteReadOnlyOuputFiles>`  
  
 Dokud tento krok následného zpracování neupravíte, při přepsání souboru se do seznamu chyb zaprotokoluje upozornění.  
  
## <a name="customizing-the-build-process"></a>Přizpůsobení procesu sestavení  
 Transformace textu se provede před všemi ostatními úlohami v procesu sestavení. Můžete definovat úkoly, které jsou vyvolány před a po transformaci nastavení vlastností `$(BeforeTransform)` a `$(AfterTransform)`:  
  
```  
<PropertyGroup>  
    <BeforeTransform>CustomPreTransform</BeforeTransform>  
    <AfterTransform>CustomPostTransform</AfterTransform>  
  </PropertyGroup>  
  <Target Name="CustomPreTransform">  
    <Message Text="In CustomPreTransform..." Importance="High" />  
  </Target>  
  <Target Name="CustomPostTransform">  
    <Message Text="In CustomPostTransform..." Importance="High" />  
  </Target>  
```  
  
 V `AfterTransform`, můžete odkazovat seznam souborů:  
  
-   GeneratedFiles – seznam souborů zapsaných procesem. U souborů, které přepsaly existující soubory určené jen pro čtení, bude mít %(GeneratedFiles.ReadOnlyFileOverwritten) hodnotu true. Tyto soubory lze rezervovat ze správy zdrojového kódu.  
  
-   NonGeneratedFiles – seznam souborů určených jen pro čtení, které nebyly přepsány.  
  
 Lze například definovat úlohu, která rezervuje GeneratedFiles.  
  
## <a name="outputfilepath-and-outputfilename"></a>OutputFilePath a OutputFileName  
 Tyto vlastnosti používá pouze nástroj MSBuild. Neovlivňují generování kódu v sadě Visual Studio. Slouží k přesměrování vygenerovaného výstupního souboru do jiné složky nebo souboru. Cílová složka již musí existovat.  
  
```xml  
<ItemGroup>  
  <None Include="MyTemplate.tt">  
    <Generator>TextTemplatingFileGenerator</Generator>  
    <OutputFilePath>MyFolder</OutputFilePath>  
    <LastGenOutput>MyTemplate.cs</LastGenOutput>  
  </None>  
</ItemGroup>  
```  
  
 Je užitečné složku pro přesměrování`$(IntermediateOutputPath).`  
  
 Zadáte-li název výstupního souboru, bude mít přednost před příponou zadanou v direktivě output v šablonách.  
  
```xml  
<ItemGroup>  
  <None Include="MyTemplate.tt">  
    <Generator>TextTemplatingFileGenerator</Generator>  
    <OutputFileName>MyOutputFileName.cs</OutputFileName>  
    <LastGenOutput>MyTemplate.cs</LastGenOutput>  
  </None>  
</ItemGroup>  
```  
  
 Zadání Název_výstupního_souboru nebo OutputFilePath se nedoporučuje, pokud jsou také transformace šablony uvnitř VS pomocí transformace všechny nebo spuštění generátoru jeden soubor. Skončíte s odlišnými cestami souborů v závislosti na tom, jak jste transformaci spustili. To může být velmi matoucí.  
  
## <a name="adding-reference-and-include-paths"></a>Přidání odkazu a cest k vkládaným souborům  
 Hostitel má nastavenu výchozí sadu cest, kde hledá sestavení odkazovaná v šablonách. Tuto sadu přidáte takto:  
  
```  
<ItemGroup>  
    <T4ReferencePath Include="$(VsIdePath)PublicAssemblies\" />  
    <!-- Add more T4ReferencePath items here -->  
</ItemGroup>  
```  
  
 Chcete-li nastavit složky, ve kterých se budou hledat vkládané soubory, zadejte seznam s prvky oddělenými středníkem. Obvykle složku přidáte do existujícího seznamu složek.  
  
```  
<PropertyGroup>  
    <IncludeFolders>  
$(IncludeFolders);$(MSBuildProjectDirectory)\Include;AnotherFolder;And\Another</IncludeFolders>  
</PropertyGroup>  
  
```  
  
##  <a name="parameters"></a>Předat data kontextu sestavení do šablony  
 Hodnoty parametru lze nastavit v souboru projektu. Například můžete předat [sestavení](../msbuild/msbuild-properties.md) vlastnosti a [proměnné prostředí](../msbuild/how-to-use-environment-variables-in-a-build.md):  
  
```xml  
<ItemGroup>  
  <T4ParameterValues Include="ProjectFolder">  
    <Value>$(ProjectDir)</Value>  
    <Visible>false</Visible>  
  </T4ParameterValues>  
</ItemGroup>  
```  
  
 V textové šablony, nastavte `hostspecific` v – direktiva šablony. Použití [parametr](../modeling/t4-parameter-directive.md) pro získání hodnoty:  
  
```  
<#@template language="c#" hostspecific="true"#>  
<#@ parameter type="System.String" name="ProjectFolder" #>  
The project folder is: <#= ProjectFolder #>  
  
```  
  
 Direktivy procesor, můžete volat <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost.ResolveParameterValue%2A>:  
  
```csharp  
string value = Host.ResolveParameterValue("-", "-", "parameterName");  
```  
  
```vb  
Dim value = Host.ResolveParameterValue("-", "-", "parameterName")  
```  
  
> [!NOTE]
>  `ResolveParameterValue`získá data z `T4ParameterValues` pouze při použití nástroje MSBuild. Při transformaci šablony pomocí sady Visual Studio budou mít parametry výchozí hodnoty.  
  
##  <a name="msbuild"></a>Pomocí vlastnosti projektu v sestavení a direktivy začlenění  
 Visual Studio makra jako $(solutiondir) – nefungují v nástroji MSBuild. Místo toho můžete použít vlastnosti projektu.  
  
 Úpravou souboru .csproj nebo .vbproj definujte vlastnost projektu. Tento příklad definuje vlastnost s názvem `myLibFolder`:  
  
```xml  
<!-- Define a project property, myLibFolder: -->  
<PropertyGroup>  
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myLibFolder">  
      <Value>$(myLibFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 Nyní můžete vlastnost projektu použít v direktivách assembly a include:  
  
```  
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>  
<#@ include file="$(myLibFolder)\MyIncludeFile.t4" #>  
```  
  
 Tyto direktivy získají z T4parameterValues hodnoty v hostitelích MSBuild i Visual Studio.  
  
## <a name="q--a"></a>Dotazy a odpovědi  
 **Proč byste měli k transformaci šablony na serveru sestavení? Šablony v sadě Visual Studio I již transformovat, než po kontrole v kódu.**  
  
 Pokud aktualizujete součástí souboru nebo jiného souboru, přečtěte si šablonou, Visual Studio nepodporuje transformaci souboru. Transformace šablony jako součást sestavení zajišťuje, že všechno, co je aktuální.  
  
 **Co další možnosti jsou pro transformace textových šablon?**  
  
-   [Texttransform – nástroj](../modeling/generating-files-with-the-texttransform-utility.md) lze použít v příkazu skripty. Ve většině případů je jednodušší použít MSBuild.  
  
-   [Volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
  
-   [Návrh textové šablony](../modeling/design-time-code-generation-by-using-t4-text-templates.md) jsou transformovány Visual Studio.  
  
-   [Spuštění textové šablony čas](../modeling/run-time-text-generation-with-t4-text-templates.md) jsou transformovány v době běhu ve vaší aplikaci.  
  
## <a name="read-more"></a>Další informace  
 Dobrý návod poskytuje šablona T4 nástroje MSbuild, $(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets.  
  
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)  
  
 [Oleg Sych: Principy T4:MSBuild integrace](http://www.olegsych.com/2010/04/understanding-t4-msbuild-integration/)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

