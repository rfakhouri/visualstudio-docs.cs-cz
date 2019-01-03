---
title: Uidmanager – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93b3c571d8c68eee8ee00475fad8bda2b5b2ec65
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53989125"
---
# <a name="uidmanager-task"></a>Uidmanager – úloha
<xref:Microsoft.Build.Tasks.Windows.UidManager> Úlohu kontroluje, aktualizuje nebo odebere jedinečné identifikátory (UID), aby bylo možné lokalizovat všechny [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] prvky, které jsou zahrnuté ve zdroji [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
| Parametr | Popis |
|-------------------------| - |
| `IntermediateDirectory` | Volitelné **řetězec** parametru.<br /><br /> Určuje adresář, který slouží k zálohování zdroje [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, které jsou určeny **MarkupFiles** parametru. |
| `MarkupFiles` | Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje zdroj [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory, které chcete zahrnout do UID kontrola, aktualizace nebo odebrání. |
| `Task` | Vyžaduje **řetězec** parametru.<br /><br /> Určuje úlohu správy UID, který chcete provést. Platné možnosti jsou **zkontrolujte**, **aktualizace**, nebo **odebrat**. |
  
## <a name="example"></a>Příklad  
 V následujícím příkladu <xref:Microsoft.Build.Tasks.Windows.UidManager> úkol zkontroluje, jestli zadaný zdroj [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory obsahují [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] prvky, které mají odpovídající identifikátory UID.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Postupy: Lokalizace aplikace](/dotnet/framework/wpf/advanced/how-to-localize-an-application)