---
title: Uidmanager – úloha | Dokumentace Microsoftu
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
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 497c8f2ff8defd0acdf943f4856f0195e50366ce
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59656827"
---
# <a name="uidmanager-task"></a>UidManager – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.UidManager> Úlohu kontroluje, aktualizuje nebo odebere jedinečné identifikátory (UID), aby bylo možné lokalizovat všechny [!INCLUDE[TLA#tla_xaml](../includes/tlasharptla-xaml-md.md)] prvky, které jsou zahrnuté ve zdroji [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`IntermediateDirectory`|Volitelné **řetězec** parametru.<br /><br /> Určuje adresář, který slouží k zálohování zdroje [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory, které jsou určeny **MarkupFiles** parametru.|  
|`MarkupFiles`|Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje zdroj [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory, které chcete zahrnout do UID kontrola, aktualizace nebo odebrání.|  
|`Task`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje úlohu správy UID, který chcete provést. Platné možnosti jsou **zkontrolujte**, **aktualizace**, nebo **odebrat**.|  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu <xref:Microsoft.Build.Tasks.Windows.UidManager> úkol zkontroluje, jestli zadaný zdroj [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] soubory obsahují [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] prvky, které mají odpovídající identifikátory UID.  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [Postupy: Lokalizace aplikace](http://msdn.microsoft.com/library/5001227e-9326-48a4-9dcd-ba1b89ee6653)
