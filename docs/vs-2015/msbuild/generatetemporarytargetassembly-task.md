---
title: Generatetemporarytargetassembly – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2ce412fdeb8d466708f3231cba14718d13720c69
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65676654"
---
# <a name="generatetemporarytargetassembly-task"></a>GenerateTemporaryTargetAssembly – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly> Úloh generuje sestavení, pokud se alespoň jeden [!INCLUDE[TLA#tla_xaml](../includes/tlasharptla-xaml-md.md)] stránky v projektu odkazuje na typ, který je deklarován místně v daném projektu. Generované sestavení se odebere po dokončení procesu sestavení, nebo pokud proces sestavení se nezdaří.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AssemblyName`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje krátký název sestavení, které se generuje pro projekt a je také název cílového sestavení, který je dočasně generován. Například, pokud projekt vygeneruje [!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)] spustitelný soubor, jehož název je **WinExeAssembly.exe**, **AssemblyName** parametr má hodnotu **WinExeAssembly**.|  
|`CompileTargetName`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje název [!INCLUDE[TLA#tla_msbuild](../includes/tlasharptla-msbuild-md.md)] cíl, který se používá ke generování sestavení ze souborů zdrojového kódu. Typická hodnota **CompileTargetName** je **CoreCompile**.|  
|`CompileTypeName`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje typ kompilaci, která se provádí v cíli, která je zadána **CompileTargetName** parametru. Pro **CoreCompile** cíl, tato hodnota je **kompilaci**.|  
|`CurrentProject`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje úplnou cestu [!INCLUDE[TLA2#tla_msbuild](../includes/tla2sharptla-msbuild-md.md)] soubor projektu pro projekt, který vyžaduje dočasné cílového sestavení.|  
|`GeneratedCodeFiles`|Volitelné **[] ITaskItem** parametru.<br /><br /> Určuje seznam spravovaného kódu specifické pro jazyk soubory, které byly vytvořeny [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md) úloh.|  
|`IntermediateOutputPath`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje adresář, generovaný dočasné cílového sestavení.|  
|`MSBuildBinPath`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje umístění **MSBuild.exe**, která se vyžaduje pro kompilaci dočasné cílového sestavení.|  
|`ReferencePath`|Volitelné **[] ITaskItem** parametru.<br /><br /> Určuje seznam sestavení, cestu a název souboru, který je odkazováno dle typy, které jsou kompilovány do sestavení dočasný cílový.|  
|`ReferencePathTypeName`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje parametr, který je používán cíl kompilace (**CompileTargetName**) parametr, který určuje seznam odkazů na sestavení (**ReferencePath**). Odpovídající hodnota je **ReferencePath**.|  
  
## <a name="remarks"></a>Poznámky  
 První fáze kompilace kódu, který běží podle [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md), zkompiluje [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory do binárního formátu. V důsledku toho kompilátor musí seznam odkazovaných sestavení, které obsahují typy, které jsou používány [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory. Nicméně pokud [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubor používá typ, který je definován ve stejném projektu, odpovídající sestavení pro tento projekt není vytvořeno, dokud sestavení projektu. Proto se odkaz na sestavení nelze zadat při prvním průchodu kód kompilace.  
  
 Místo toho **MarkupCompilePass1** odloží převodu [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] předat soubory, které obsahují odkazy na typy v rámci jednoho projektu do druhého kompilace kódu, který provádí [markupcompilepass2 –](../msbuild/markupcompilepass2-task.md). Před **markupcompilepass2 –** se provedl a vytvořil dočasný sestavení je generováno. Toto sestavení obsahuje typy, které jsou používány [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory, jehož značky kompilace pass byla odložena. Odkaz na vygenerované sestavení je k dispozici na **markupcompilepass2 –** během spuštění umožňující odložené kompilace [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory převést do binárního formátu.  
  
## <a name="example"></a>Příklad  
 Následující příklad generuje dočasné sestavení, protože `Page1.xaml` obsahuje odkaz na typ, který je ve stejném projektu.  
  
```  
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
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](https://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [Přehled aplikací Prohlížeče WPF XAML](https://msdn.microsoft.com/library/3a7a86a8-75d5-4898-96b9-73da151e5e16)
