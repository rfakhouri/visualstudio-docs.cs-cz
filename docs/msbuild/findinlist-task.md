---
title: Findinlist – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c2f6c5f14f6eff818a265e097f02e2bc76c7372
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996669"
---
# <a name="findinlist-task"></a>FindInList – úloha
V zadaném seznamu vyhledá položku, která má odpovídající itemspec.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry [findinlist – úloha](../msbuild/findinlist-task.md).

|Parametr|Popis|
|---------------|-----------------|
|`CaseSensitive`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, hledání se malá a velká písmena; jinak vrátí hodnotu, není. Výchozí hodnota je `true`.|
|`FindLastMatch`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, vraťte poslední shody; jinak vrátí první shoda. Výchozí hodnota je `false`.|
|`ItemFound`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` jen pro čtení výstupního parametru.<br /><br /> První odpovídající položka nalezena v seznamu, pokud existuje.|
|`ItemSpecToFind`|Vyžaduje `String` parametru.<br /><br /> Itemspec pro hledání.|
|`List`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Seznam, ve kterých chcete hledat itemspec.|
|`MatchFileNameOnly`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, porovnávat pouze soubor název část itemspec; v opačném případě porovnání celý itemspec. Výchozí hodnota je `true`.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)