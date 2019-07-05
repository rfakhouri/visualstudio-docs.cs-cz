---
title: Úloha CustomBuild | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.custombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CustomBuild task
- CustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 04f33f3852f051e1f492cb2b6dca44fcdb260e11
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2019
ms.locfileid: "67587007"
---
# <a name="custombuild-task"></a>CustomBuild úkolu

Zabalí nástroj kompilátoru Visual C++ cmd.exe. Tato třída je odvozena z [TrackedVCToolTask](../msbuild/trackedvctooltask-base-class.md), ale nepoužívá sledování souborů ke zjištění závislostem. Všechny závislosti by měl být explicitně zadané jako AdditionalDependencies pro přírůstkové sestavení funguje správně.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **CustomBuild** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**BuildSuffix**|Volitelné **řetězec** parametru.|
|**Zdroje**|Vyžaduje **[] ITaskItem** parametru.|
|**TrackerLogDirectory**|Volitelné **řetězec** parametru.|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
