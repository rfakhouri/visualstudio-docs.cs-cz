---
title: "Resolvenativereference – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
caps.latest.revision: "9"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5d2b7cffec4dc9e321ab9468ce57232e82087eab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="resolvenativereference-task"></a>ResolveNativeReference – úloha
Přeloží nativní odkazy. Implementuje <xref:Microsoft.Build.Tasks.ResolveNativeReference> třídy. Tato třída podporuje infrastrukturu rozhraní .NET Framework, která není určena pro použití přímo z vašeho kódu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `ResolveNativeReference` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AdditionalSearchPaths`|Požadovaný parametr <xref:System.String?displayProperty=fullName>`[]`.<br /><br /> Získá nebo nastaví cesty hledání pro řešení identit sestavení nativní odkazy.|  
|`ContainedComComponents`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví komponenty COM nativní sestavení.|  
|`ContainedLooseEtcFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví volné apod soubory uvedené v manifestu nativní.|  
|`ContainedLooseTlbFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví soubory přijít .tlb nativní sestavení.|  
|`ContainedPrerequisiteAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví sestavení, která se musí vyskytovat před použitím v manifestu.|  
|`ContainedTypeLibraries`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví knihoven typů nativní sestavení.|  
|`ContainingReferenceFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví referenčních souborů.|  
|`NativeReferences`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Získá nebo nastaví odkazy na nativní sestavení Win32.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)