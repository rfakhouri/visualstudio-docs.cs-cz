---
title: "Findinlist – úloha | Microsoft Docs"
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
- FindInList task [MSBuild]
- MSBuild, FindInList task
ms.assetid: d49b9f84-52a2-4242-9269-b741a7a7e9f7
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ccf4f6b8f07da67af061c101f7f7b6500de48f73
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="findinlist-task"></a>FindInList – úloha
V zadaného seznamu vyhledá položku, která obsahuje odpovídající itemspec.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry [findinlist – úloha](../msbuild/findinlist-task.md).  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`CaseSensitive`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`hledání je malá a velká písmena jinak, není. Výchozí hodnota je `true`.|  
|`FindLastMatch`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vrátí poslední shody; jinak vrátí první shodu. Výchozí hodnota je `false`.|  
|`ItemFound`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` jen pro čtení výstupní parametr.<br /><br /> První odpovídající nalezených položek v seznamu, pokud existuje.|  
|`ItemSpecToFind`|Požadované `String` parametr.<br /><br /> Itemspec pro vyhledávání.|  
|`List`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Seznam, do kterého chcete vyhledat itemspec.|  
|`MatchFileNameOnly`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, odpovídající jenom část názvu souboru toho itemspec; jinak odpovídající celou itemspec. Výchozí hodnota je `true`.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)