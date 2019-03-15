---
title: Úloha ParallelCustomBuild | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.parallelcustombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), ParallelCustomBuild task
- ParallelCustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 506ead6680bd9a0aaaf38d6959da02a14dfee337
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58071119"
---
# <a name="parallelcustombuild-task"></a>ParallelCustomBuild úkolu

Spouštění paralelních instancí [CustomBuild úloh](../msbuild/custombuild-task.md).

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **ParallelCustomBuild** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**BreakOnFirstFailure**|Volitelné **bool** parametru.|
|**MaxItemsInBatch**|Volitelné **int** parametru.|
|**MaxProcesses**|Volitelné **int** parametru.|
|**Zdroje**|Vyžaduje **[] ITaskItem** parametru.|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)