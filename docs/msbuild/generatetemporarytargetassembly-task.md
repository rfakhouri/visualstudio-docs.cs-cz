---
title: "GenerateTemporaryTargetAssembly – úloha | Microsoft Docs"
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
- build process [WPF MSBuild], XAML page refers to a locally declared type
- GenerateTemporaryTargetAssembly task [WPF MSBuild]
- GenerateTemporaryTargetAssembly task [WPF MSBuild], parameters
- creating an assembly [WPF MSBuild], XAML page refers to a locally declared type
ms.assetid: 92b6539c-6897-45e0-8989-0c234bbfe782
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: dd570e81198f63a22f196e04a5d0a321fc3c6d21
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="generatetemporarytargetassembly-task"></a>GenerateTemporaryTargetAssembly – úloha
<xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly> Úloh generuje sestavení, pokud alespoň jeden [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] stránky v projektu odkazuje na typ, který je deklarován místně v tomto projektu. Po dokončení procesu sestavení, nebo pokud proces sestavení selže, odeberou se vygenerované sestavení.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AssemblyName`|Požadované **řetězec** parametr.<br /><br /> Určuje krátký název sestavení, které se generuje pro projekt a je také název cílové sestavení, které se dočasně vygeneruje. Například, pokud generuje projektu [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] spustitelný soubor, jehož název je **WinExeAssembly.exe**, **AssemblyName** parametru má hodnotu **WinExeAssembly**.|  
|`CompileTargetName`|Požadované **řetězec** parametr.<br /><br /> Určuje název [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] cíl, který se používá ke generování sestavení z soubory zdrojového kódu. Typické hodnota **CompileTargetName** je **CoreCompile**.|  
|`CompileTypeName`|Požadované **řetězec** parametr.<br /><br /> Určuje typ kompilace, které se provádí pomocí cíl, který je zadán **CompileTargetName** parametr. Pro **CoreCompile** cíl, tato hodnota je **zkompilovat**.|  
|`CurrentProject`|Požadované **řetězec** parametr.<br /><br /> Určuje úplnou cestu [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] soubor projektu pro projekt, který vyžaduje dočasné cíl sestavení.|  
|`GeneratedCodeFiles`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam souborů pro specifický jazyk spravovaného kódu, které byly vygenerovány [markupcompilepass1 –](../msbuild/markupcompilepass1-task.md) úloh.|  
|`IntermediateOutputPath`|Požadované **řetězec** parametr.<br /><br /> Určuje adresář, který generovaný dočasné cíl sestavení.|  
|`MSBuildBinPath`|Požadované **řetězec** parametr.<br /><br /> Určuje umístění **MSBuild.exe**, které je požadované ke kompilaci dočasné cíl sestavení.|  
|`ReferencePath`|Volitelné **[ITaskItem]** parametr.<br /><br /> Určuje seznam sestavení, cesta a název souboru, který se odkazuje typy, které jsou zkompilovány do dočasné cíl sestavení.|  
|`ReferencePathTypeName`|Požadované **řetězec** parametr.<br /><br /> Určuje parametr, který je používán cíl kompilace (**CompileTargetName**) parametr, který určuje seznam odkazů na sestavení (**ReferencePath**). Je příslušná hodnota **ReferencePath**.|  
  
## <a name="remarks"></a>Poznámky  
 První fáze kompilace kódu, který běží podle [markupcompilepass1 –](../msbuild/markupcompilepass1-task.md), zkompiluje [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory do binárního formátu. V důsledku toho vyžaduje kompilátor seznam odkazované sestavení, které obsahují typy používané [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory. Ale pokud [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubor používá typ, který je definován v rámci jednoho projektu, odpovídající sestavení pro tento projekt vytvořen až sestavení projektu. Odkaz na sestavení proto nelze zadat během první fáze kompilace kódu.  
  
 Místo toho **markupcompilepass1 –** odkládat údaje převodu [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] předat soubory, které obsahují odkazy na typy ve stejném projektu a druhý kompilace kódu, který spouští [markupcompilepass2 –](../msbuild/markupcompilepass2-task.md). Před **markupcompilepass2 –** je provést, je generována dočasné sestavení. Toto sestavení obsahuje typy, které jsou používány [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, jejichž průchodu kompilace kódu byla odložena. Odkaz na sestavení vygenerovaný zajišťuje **markupcompilepass2 –** spuštění povolit odloženou kompilace [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, které má být převeden do binárního formátu.  
  
## <a name="example"></a>Příklad  
 Následující příklad generuje dočasné sestavení, protože `Page1.xaml` obsahuje odkaz na typ, který je ve stejném projektu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask  
    TaskName="Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="GenerateTemporaryTargetAssemblyTask">  
    <GenerateTemporaryTargetAssembly  
      AssemblyName="WPFMSBuildSample"  
      CompileTargetName="CoreCompile"  
      CompileTypeName="Compile"  
      CurrentProject="FullBuild.proj"  
      GeneratedCodeFiles="obj\debug\app.g.cs;obj\debug\Page1.g.cs;obj\debug\Page2.g.cs"  
      ReferencePath="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll"  
      IntermediateOutputPath=".\obj\debug\"  
      MSBuildBinPath="$(MSBuildBinPath)"  
      ReferencePathTypeName="ReferencePath"/>  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Přehled aplikací Prohlížeče WPF XAML](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)