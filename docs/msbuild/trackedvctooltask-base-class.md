---
title: Třída TrackedVCToolTask | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 4a4044416131a27ca313d10d02404094c5f5e219
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62938866"
---
# <a name="trackedvctooltask-base-class"></a>Základní třída TrackedVCToolTask

Nakonec dědí celou řadu úloh <xref:Microsoft.Build.Utilities.Task> třídy a [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) třídy. Tato třída přidává několik parametrů na úlohy, které jsou odvozeny z [VCToolTask](../msbuild/vctooltask-base-class.md). Tyto parametry jsou uvedeny v tomto dokumentu.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **TrackedVCToolTask** základní třídy.

|Parametr|Popis|
|---------------|-----------------|
|**DeleteOutputOnExecute**|Volitelné **bool** parametru.|
|**EnableExecuteTool**|Volitelné **bool** parametru.|
|**ExcludedInputPaths**|Volitelné **[] ITaskItem** parametru.|
|**MinimalRebuildFromTracking**|Volitelné **bool** parametru.|
|**PathOverride**|Volitelné **řetězec** parametru.|
|**PostBuildTrackingCleanup**|Volitelné **bool** parametru.|
|**RootSource**|Volitelné **řetězec** parametru.|
|**SkippedExecution**|Volitelné **bool** výstupní parametr.|
|**SourcesCompiled**|Volitelné **[] ITaskItem** výstupní parametr.|
|**TLogCommandFile**|Volitelné **ITaskItem** parametru.|
|**TLogReadFiles**|Volitelné **[] ITaskItem** parametru.|
|**TLogWriteFiles**|Volitelné **[] ITaskItem** parametru.|
|**ToolArchitecture**|Volitelné **řetězec** parametru.|
|**TrackCommandLines**|Volitelné **bool** parametru.|
|**TrackFileAccess**|Volitelné **bool** parametru.|
|**TrackedInputFilesToIgnore**|Volitelné **[] ITaskItem** parametru.|
|**TrackedOutputFilesToIgnore**|Volitelné **[] ITaskItem** parametru.|
|**TrackerFrameworkPath**|Volitelné **řetězec** parametru.|
|**TrackerSdkPath**|Volitelné **řetězec** parametru.|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)<br/>
[Úlohy](../msbuild/msbuild-tasks.md)