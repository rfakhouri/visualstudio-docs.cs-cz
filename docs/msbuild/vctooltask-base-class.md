---
title: Třída VCToolTask | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 4c7cc3490735dbd9ac43cd43555ec673cc3afccd
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58071131"
---
# <a name="vctooltask-base-class"></a>Základní třída VCToolTask

Nakonec dědí celou řadu úloh <xref:Microsoft.Build.Utilities.Task> třídy a [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) třídy. Tato třída přidává několik parametrů na úlohy, které jsou odvozeny z nich. Tyto parametry jsou uvedeny v tomto dokumentu.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **VCToolTask** základní třídy.

|Parametr|Popis|
|---------------|-----------------|
|**ActiveToolSwitchesValues**|Volitelné **slovníku\<string, ToolSwitch >** parametru.|
|**AdditionalOptions**|Volitelné **řetězec** parametru.|
|**EffectiveWorkingDirectory**|Volitelné **řetězec** parametru.|
|**EnableErrorListRegex**|Volitelné **bool** parametru.<br/><br/>Výchozí hodnota je `true`.|
|**ErrorListRegex**|Volitelné **[] ITaskItem** parametru.|
|**ErrorListListExclusion**|Volitelné **[] ITaskItem** parametru.|
|**GenerateCommandLine**|Volitelné **řetězec** parametru.<br/><br/>Používá hodnoty **CommandLineFormat** *formátu* [výchozí = CommandLineFormat.ForBuildLog] a **EscapeFormat** *escapeFormat* [ Výchozí = EscapeFormat.Default].|
|**GenerateCommandLineExceptSwitches**|Volitelné **řetězec** parametru.<br/><br/>Používá hodnoty **string []** *switchesToRemove*, **CommandLineFormat** *formátu* [výchozí = CommandLineFormat.ForBuildLog], a **EscapeFormat** *escapeFormat* [výchozí = EscapeFormat.Default].|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)<br/>
[Úlohy](../msbuild/msbuild-tasks.md)