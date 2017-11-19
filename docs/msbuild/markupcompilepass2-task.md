---
title: "Markupcompilepass2 – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- performing second-pass markup [WPF MSBuild], MarkupCompilePass2 task
- MarkupCompilePass2 task [WPF MSBuild]
- MarkupCompilePass2 task [WPF MSBuild], parameters
ms.assetid: 1d25689a-d21f-4b05-be26-95aa0ed4fd03
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a8b25cc2ec7f0a12eb5b7e3be85251906308781d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="markupcompilepass2-task"></a>MarkupCompilePass2 – úloha
<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> Úlohy kompilace značek druhého průchodu provádí [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] soubory, které odkazují na typy ve stejném projektu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AlwaysCompileMarkupFilesInSeparateDomain`|Volitelné **Boolean** parametr.<br /><br /> Určuje, zda chcete spustit úlohu v samostatném <xref:System.AppDomain>. Pokud tento parametr vrátí **false**, úloha běží ve stejné <xref:System.AppDomain> jako [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)], a běží rychleji. Pokud vrátí parametr **true**, bude spuštěna úloha za sekundu <xref:System.AppDomain> , je izolovaná od [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] a jsou pomalejší.|  
|`AssembliesGeneratedDuringBuild`|Volitelné **řetězec []** parametr.<br /><br /> Určuje odkazy na sestavení, které změnit během procesu sestavení. Například [!INCLUDE[TLA#tla_visualstu2005](../msbuild/includes/tlasharptla_visualstu2005_md.md)] řešení může obsahovat jeden projekt, který odkazuje na kompilované výstup jiného projektu. V takovém případě můžete kompilované výstup druhý projektu přidán do **AssembliesGeneratedDuringBuild**.<br /><br /> Poznámka: **AssembliesGeneratedDuringBuild** musí obsahovat odkazy na kompletní sadu sestavení, které jsou generovány nástrojem sestavení řešení.|  
|`AssemblyName`|Požadované **řetězec** parametr.<br /><br /> Určuje krátký název sestavení, které se generuje pro projekt. Například, pokud je generování projektu [!INCLUDE[TLA#tla_win](../msbuild/includes/tlasharptla_win_md.md)] spustitelný soubor, jehož název je **WinExeAssembly.exe**, **AssemblyName** parametru má hodnotu **WinExeAssembly**.|  
|`GeneratedBaml`|Volitelné **[ITaskItem]** výstupní parametr.<br /><br /> Obsahuje seznam generované soubory v [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát.|  
|`KnownReferencePaths`|Volitelné **řetězec []** parametr.<br /><br /> Určuje odkazy na sestavení, které jsou během procesu sestavení nikdy změnit. Zahrnuje sestavení, které se nacházejí ve [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)]v [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] instalační adresář a tak dále.|  
|`Language`|Požadované **řetězec** parametr.<br /><br /> Určuje spravovaný jazyk, který podporuje kompilátoru. Platné možnosti jsou **C#**, **VB**, **JScript**, a **C++**.|  
|`LocalizationDirectivesToLocFile`|Volitelné **řetězec** parametr.<br /><br /> Určuje, jak generovat informace o lokalizaci pro každý zdroj [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] souboru. Platné možnosti jsou **žádné**, **CommentsOnly**, a **všechny**.|  
|`OutputPath`|Požadované **řetězec** parametr.<br /><br /> Určuje adresář, ve kterém vygenerovaného [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] jsou generovány binární formát souborů.|  
|`OutputType`|Požadované **řetězec** parametr.<br /><br /> Určuje typ sestavení, který je generovaný projektu. Platné možnosti jsou **winexe**, **exe**, **knihovny**, a **netmodule**.|  
|`References`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam odkazů na ze souborů na sestavení, které obsahují typy, které se používají v [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory. Je jeden odkaz na sestavení, které vygenerovalo <xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly> úloh, které musí spustit před <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> úloh.|  
|`RootNamespace`|Volitelné **řetězec** parametr.<br /><br /> Určuje kořenový obor názvů pro třídy, které jsou v projektu. **RootNamespace** se používá jako výchozí obor názvů generovaného spravovaného kódu souboru, když k odpovídající položce [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor neobsahuje `x:Class` atribut.|  
|`XAMLDebuggingInformation`|Volitelné **Boolean** parametr.<br /><br /> Když **true**, je generována a součástí zkompilovaný diagnostické informace [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] Chcete-li docílit ladění.|  
  
## <a name="remarks"></a>Poznámky  
 Před spuštěním **markupcompilepass2 –**, musíte vygenerovat dočasné sestavení, které obsahuje typy, které jsou používány [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory byly odložení jejichž průchodu kompilace kódu. Generování dočasného sestavení tak, že spustíte **GenerateTemporaryTargetAssembly** úloh.  
  
 Odkaz na generovaného dočasné sestavení zajišťuje <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> při spuštění, což [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, jejichž kompilace byla odložena v první kompilace kódu předat nyní být zkompilovány do binárního formátu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> úlohu pro druhý předat kompilace.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass2"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MarkupCompilePass2Task">  
    <MarkupCompilePass2   
      AssemblyName="WPFMSBuildSample"  
      Language="C#"  
      OutputType="WinExe"  
      OutputPath="obj\Debug\"  
      References=".\obj\debug\WPFMSBuildSample.exe;c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Přehled aplikace prohlížeče WPF XAML](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)