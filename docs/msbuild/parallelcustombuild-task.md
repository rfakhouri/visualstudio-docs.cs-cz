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
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 54623ab1c58d85de55c5b8a24384bf0be46f1a61
ms.sourcegitcommit: d78821f8c353e0102b1554719f549f32dffac71b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58515123"
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