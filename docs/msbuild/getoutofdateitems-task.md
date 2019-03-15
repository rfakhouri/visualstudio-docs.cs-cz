---
title: Úloha GetOutOfDateItems | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.getoutofdateitems
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), GetOutOfDateItems task
- GetOutOfDateItems task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 668dddcd0854869c9ede7bf96c092d415f41dd17
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58071120"
---
# <a name="getoutofdateitems-task"></a>GetOutOfDateItems úkolu

Pomocné rutiny úkolu, který čte staré tlogs zapíše nové tlogs a vrátí sadu položek, které nejsou aktuální.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **GetOutOfDateItems** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**CheckForInterdependencies**|Volitelné **bool** parametru.|
|**CommandMetadataName**|Volitelné **řetězec** parametru.|
|**DependenciesMetadataName**|Volitelné **řetězec** parametru.|
|**HasInterdependencies**|Volitelné **bool** výstupní parametr.|
|**OutOfDateSources**|Volitelné **[] ITaskItem** výstupní parametr.|
|**OutputsMetadataName**|Vyžaduje **řetězec** parametru.|
|**Zdroje**|Volitelné **[] ITaskItem** parametru.|
|**TLogDirectory**|Vyžaduje **řetězec** parametru.|
|**TLogNamePrefix**|Vyžaduje **řetězec** parametru.|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)