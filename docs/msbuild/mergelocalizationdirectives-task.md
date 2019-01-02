---
title: Mergelocalizationdirectives – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64f36cadc6ee33563f516703f3bc48e81558b8ec
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959911"
---
# <a name="mergelocalizationdirectives-task"></a>Mergelocalizationdirectives – úloha
<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> Úloh sloučí atributy a komentáře lokalizace jednoho nebo víc [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binárních souborů do jediného souboru pro celé sestavení.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
| Parametr | Popis |
|------------------------------| - |
| `GeneratedLocalizationFiles` | Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje seznam souborů direktivy lokalizace pro jednotlivé soubory v [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binárním formátu. |
| `OutputFile` | Vyžaduje **řetězec** výstupní parametr.<br /><br /> Určuje výstupní cestu sestavení zkompilované lokalizace direktivy. |
  
## <a name="remarks"></a>Poznámky  
 Můžete přidat atributy a komentáře k lokalizace [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] obsah. S [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)] podporu lokalizace, můžete odstranit atributy a komentáře lokalizace a umístit je do *.loc* soubor, který je oddělený od vygenerované sestavení. Můžete to provést pomocí **LocalizationPropertyStorage** atribut. Další informace o atributy a komentáře, lokalizace a **LocalizationPropertyStorage**, naleznete v tématu [atributy a komentáře lokalizace](/dotnet/framework/wpf/advanced/localization-attributes-and-comments).  
  
## <a name="example"></a>Příklad  
 Následující příklad sloučí komentáře lokalizace několik [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binárních souborů do jediného *.loc* souboru.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také:  
[Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)  
[WPF MSBuild – referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)  
[Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
[Referenční dokumentace úlohy nástroje MSBuild](../msbuild/msbuild-task-reference.md)  
[Sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)  
