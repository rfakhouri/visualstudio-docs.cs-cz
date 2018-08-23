---
title: Resolvenativereference – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d06171281706b2395cbac0c98b5b8a76c4da363c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631408"
---
# <a name="resolvenativereference-task"></a>ResolveNativeReference – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [resolvenativereference – úloha](https://docs.microsoft.com/visualstudio/msbuild/resolvenativereference-task).  
  
  
Nativní odkazy řeší. Implementuje <xref:Microsoft.Build.Tasks.ResolveNativeReference> třídy. Tato třída podporuje infrastrukturu rozhraní .NET Framework, která není určena pro použití přímo v kódu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `ResolveNativeReference` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AdditionalSearchPaths`|Vyžaduje [String] (<!-- TODO: review code entity reference <xref:assetId:///String?qualifyHint=False&amp;autoUpgrade=True>  -->)`[]` parametru.<br /><br /> Získá nebo nastaví cesty hledání pro řešení identit sestavení pro nativní odkazy.|  
|`ContainedComComponents`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví komponenty modelu COM nativní sestavení.|  
|`ContainedLooseEtcFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví volné Etc soubory uvedené v nativní manifest.|  
|`ContainedLooseTlbFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví soubory .tlb dojde ke ztrátě nativní sestavení.|  
|`ContainedPrerequisiteAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví sestavení, která se musí nacházet před použitím v manifestu.|  
|`ContainedTypeLibraries`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví typ knihovny nativní sestavení.|  
|`ContainingReferenceFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví odkaz na soubory.|  
|`NativeReferences`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Získá nebo nastaví odkazy na sestavení nativního Win32.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



