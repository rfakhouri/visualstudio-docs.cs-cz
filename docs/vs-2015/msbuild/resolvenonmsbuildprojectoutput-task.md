---
title: Resolvenonmsbuildprojectoutput – úloha | Dokumentace Microsoftu
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
- MSBuild, ResolveNonMSBuildProjectOutput task
- ResolveNonMSBuildProjectOutput task [MSBuild]
ms.assetid: a0b8fcec-8c8d-4867-85ac-5304c5108e5e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: aaf99affe9c29762aa8b47ea76419da429089b7c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68156148"
---
# <a name="resolvenonmsbuildprojectoutput-task"></a>ResolveNonMSBuildProjectOutput – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje výstupní soubory pro odkazy na projekt bez MSBuild.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `ResolveNonMSBuildProjectOutput` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`PreresolvedProjectOutputs`|Volitelné `String` parametru.<br /><br /> Určuje řetězec XML, který obsahuje přeložit výstupy projektu.|  
|`ProjectReferences`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje odkazy projektu.|  
|`ResolvedOutputPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam cest vyřešených odkazů (a zachová původní atributy odkaz na projekt).|  
|`UnresolvedProjectReferences`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam referenčních položek projektu, které nelze vyřešit pomocí preresolved seznamů výstupů.<br /><br /> Vzhledem k tomu, že Visual Studio preresolves jenom projekty bez MSBuild, to znamená, že odkazy na projekt v tomto seznamu ve formátu MSBuild.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
