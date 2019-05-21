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
ms.openlocfilehash: 6d466dec85a0bdf242120ef5e88a0d5f5d2ac48e
ms.sourcegitcommit: 0ef51e3517436a85cfb85bf492722d566ce602c4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934512"
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
