---
title: Findinlist – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- FindInList task [MSBuild]
- MSBuild, FindInList task
ms.assetid: d49b9f84-52a2-4242-9269-b741a7a7e9f7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 85d45bb5494f3cf3a4bd06103e05fb17d6f1d00b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31579001"
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