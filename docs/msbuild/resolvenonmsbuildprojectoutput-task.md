---
title: Resolvenonmsbuildprojectoutput – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a482e93bb2a4e03eac7d4b0188303f203ea05445
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013883"
---
# <a name="resolvenonmsbuildprojectoutput-task"></a>ResolveNonMSBuildProjectOutput – úloha
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
  
## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)