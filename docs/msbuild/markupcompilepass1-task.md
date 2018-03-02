---
title: "Markupcompilepass1 – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- converting XAML to binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], parameters
- converting XAML projects to compiled binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], converting XAML to binary format
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e6b15b4af1b828092504e051c7f6d1bb57b79b51
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="markupcompilepass1-task"></a>MarkupCompilePass1 – úloha

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> Úloh převede nepřekládá [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] soubory do kompilovaného binárního formátu projektu.

## <a name="task-parameters"></a>Parametry úlohy

|Parametr|Popis|
|---------------|-----------------|
|`AllGeneratedFiles`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Obsahuje kompletní seznam souborů, které jsou generované <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> úloh.|
|`AlwaysCompileMarkupFilesInSeparateDomain`|Volitelné **Boolean** parametr.<br /><br /> Určuje, zda chcete spustit úlohu v samostatném <xref:System.AppDomain>. Pokud tento parametr vrátí **false**, úloha běží ve stejné <xref:System.AppDomain> jako [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] a běží rychleji. Pokud vrátí parametr **true**, bude spuštěna úloha za sekundu <xref:System.AppDomain> , je izolovaná od [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] a jsou pomalejší.|
|`ApplicationMarkup`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje název definice aplikace [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] souboru.|
|`AssembliesGeneratedDuringBuild`|Volitelné **řetězec []** parametr.<br /><br /> Určuje odkazy na sestavení, které změnit během procesu sestavení. Řešení sady Visual Studio může například obsahovat jeden projekt, který odkazuje na kompilované výstup jiného projektu. V takovém případě můžete kompilované výstup druhý projektu přidán do **AssembliesGeneratedDuringBuild** parametr.<br /><br /> Poznámka: **AssembliesGeneratedDuringBuild** parametr musí obsahovat odkazy na kompletní sadu sestavení, které jsou generovány nástrojem sestavení řešení.|
|`AssemblyName`|Požadované **řetězec** parametr.<br /><br /> Určuje krátký název sestavení, které se generuje pro projekt. Například, pokud je generování projektu [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] spustitelný soubor, jehož název je **WinExeAssembly.exe**, **AssemblyName** parametru má hodnotu **WinExeAssembly**.|
|`AssemblyPublicKeyToken`|Volitelné **řetězec** parametr.<br /><br /> Určuje token veřejného klíče pro sestavení.|
|`AssemblyVersion`|Volitelné **řetězec** parametr.<br /><br /> Určuje číslo verze sestavení.|
|`ContentFiles`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam přijít obsahu souborů.|
|`DefineConstants`|Volitelné **řetězec** parametr.<br /><br /> Určuje, že aktuální hodnota **DefineConstants**, je uložen. která ovlivňuje cílový vytváření sestavení; Pokud tento parametr je změnit, může se změnit veřejné rozhraní API v cílové sestavení a kompilace [!INCLUDE[TLA2#tla_titlexaml](../msbuild/includes/tla2sharptla_titlexaml_md.md)] soubory, které odkazují na místní typy může být ovlivněn.|
|`ExtraBuildControlFiles`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam souborů, které řídí, zda opětovném sestavení při aktivaci <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> úloh opakovaně; opětovné sestavení se aktivuje, pokud jeden z těchto souborů změny.|
|`GeneratedBamlFiles`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Obsahuje seznam generované soubory v [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát.|
|`GeneratedCodeFiles`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Obsahuje seznam souborů generovaného spravovaného kódu.|
|`GeneratedLocalizationFiles`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Obsahuje seznam lokalizační soubory, které byly vygenerovány pro každý lokalizovatelný [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] souboru.|
|`HostInBrowser`|Volitelné **řetězec** parametr.<br /><br /> Určuje, jestli je generovaný sestavení [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)]. Platné možnosti jsou **true** a **false**. Pokud **true**, se generuje kód pro podporu hostování prohlížeče.|
|`KnownReferencePaths`|Volitelné **řetězec []** parametr.<br /><br /> Určuje odkazy na sestavení, které se nemění během procesu vytváření. Zahrnuje sestavení, které se nacházejí ve [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)]v [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] instalační adresář a tak dále.|
|`Language`|Požadované **řetězec** parametr.<br /><br /> Určuje spravovaný jazyk, který podporuje kompilátoru. Platné možnosti jsou **C#**, **VB**, **JScript**, a **C++**.|
|`LanguageSourceExtension`|Volitelné **řetězec** parametr.<br /><br /> Určuje příponu, který se připojí k rozšíření souboru generovaného spravovaného kódu:<br /><br /> `<Filename>.g<LanguageSourceExtension>`<br /><br /> Pokud **LanguageSourceExtension** není nastavený parametr s konkrétní hodnotou, bude použita výchozí příponu názvu souboru zdroje pro jazyk: **VB** pro [!INCLUDE[TLA#tla_visualb](../msbuild/includes/tlasharptla_visualb_md.md)], **.csharp** pro [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)].|
|`LocalizationDirectivesToLocFile`|Volitelné **řetězec** parametr.<br /><br /> Určuje, jak generovat informace o lokalizaci pro každý zdroj [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] souboru. Platné možnosti jsou **žádné**, **CommentsOnly**, a **všechny**.|
|`OutputPath`|Požadované **řetězec** parametr.<br /><br /> Určuje adresář, ve kterém vygenerovaného spravované soubory kódu a [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] jsou generovány binární formát souborů.|
|`OutputType`|Požadované **řetězec** parametr.<br /><br /> Určuje typ sestavení, který je generovaný projektu. Platné možnosti jsou **winexe**, **exe**, **knihovny**, a **netmodule**.|
|`PageMarkup`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] souborů do procesu.|
|`References`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam odkazů na ze souborů na sestavení, které obsahují typy, které se používají v [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory.|
|`RequirePass2ForMainAssembly`|Volitelné **Boolean** výstupní parametr.<br /><br /> Určuje, zda projekt obsahuje nepřekládá [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, které odkazují na místní typy, které jsou vloženy do hlavní sestavení.|
|`RequirePass2ForSatelliteAssembly`|Volitelné **Boolean** výstupní parametr.<br /><br /> Určuje, zda projekt obsahuje lokalizovatelný [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, které odkazují na místní typy, které jsou vloženy do hlavní sestavení.|
|`RootNamespace`|Volitelné **řetězec** parametr.<br /><br /> Určuje kořenový obor názvů pro třídy, které jsou v projektu. **RootNamespace** se používá jako výchozí obor názvů generovaného spravovaného kódu souboru, když k odpovídající položce [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor neobsahuje `x:Class` atribut.|
|`SourceCodeFiles`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam soubory kódu aktuálního projektu. V seznamu nezahrnuje soubory generované pro specifický jazyk spravovaného kódu.|
|`UICulture`|Volitelné **řetězec** parametr.<br /><br /> Určuje satelitní sestavení pro jazyková verze uživatelského rozhraní, ve kterém vygenerovaného [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát souborů jsou vloženy. Pokud **UICulture** není nastavena, vygenerovaného [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát souborů se vloží do hlavní sestavení.|
|`XAMLDebuggingInformation`|Volitelné **Boolean** parametr.<br /><br /> Když **true**, je generována a součástí zkompilovaný diagnostické informace [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] Chcete-li docílit ladění.|

## <a name="remarks"></a>Poznámky

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> Úloh obvykle zkompiluje [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] do binárního formátu a generuje soubory kódu. Pokud [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor obsahuje odkazy na typy, které jsou definované ve stejném projektu, je jeho kompilace do binárního formátu odložit **markupcompilepass1 –** do druhého průchodu kompilace kódu ( **Markupcompilepass2 –**). Tyto soubory musí mít jejich kompilace odložení, protože se musí čekat, dokud se kompilují odkazované místně definované typy. Ale pokud [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor má `x:Class` atribut <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> vygeneruje soubor kódu pro konkrétní jazyk pro ni.

A [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor je lokalizovatelný, pokud obsahuje prvky, které používají `x:Uid` atribut:

```xml
<Page x:Class="WPFMSBuildSample.Page1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Uid="Page1Uid"
    >
  ...
</Page>
```

A [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor odkazuje místně definovaný typ. Pokud deklaruje [!INCLUDE[TLA#tla_xml](../msbuild/includes/tlasharptla_xml_md.md)] obor názvů, který používá `clr-namespace` hodnotu k odkazování na obor názvů v aktuálním projektu:

```xml
<Page x:Class="WPFMSBuildSample.Page1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:localNamespace="clr-namespace:WPFMSBuildSample"
    >
    <Grid>
      <Grid.Resources>
        <localNameSpace:LocalType x:Key="localType" />
      </Grid.Resources>
      ...
    </Grid>
</Page>
```

Pokud existuje [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor lokalizovatelný, nebo odkazuje na typ místně definované, druhé fázi kompilace kódu se vyžaduje, což vyžaduje, aby spuštěná [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md) a potom [ Markupcompilepass2 –](../msbuild/markupcompilepass2-task.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje, jak převést tři `Page` [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory do binárního formátu souborů. `Page1` obsahuje odkaz na typ `Class1`, který je v kořenovém oboru názvů projektu a proto není převést na binární formát souborů v tomto průchodu kompilace kódu. Místo toho [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md) se spustí a následuje [markupcompilepass2 –](../msbuild/markupcompilepass2-task.md).

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask 
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass1" 
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="MarkupCompilePass1Task">
    <MarkupCompilePass1 
      AssemblyName="WPFMSBuildSample"
      Language="C#"
      OutputType="WinExe"
      OutputPath="obj\Debug\"
      ApplicationMarkup="App.xaml"
      PageMarkup="Page1.xaml;Page2.xaml;Page3.xaml"
      SourceCodeFiles="Class1.cs"
      References="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />
  </Target>
</Project>
```

## <a name="see-also"></a>Viz také

[Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)  
[Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)  
[Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)  
[Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)  
[Přehled aplikací Prohlížeče WPF XAML](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)