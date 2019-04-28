---
title: CombinePath – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6b73ddd4715d3abd29f87d7ef38a269d821733ba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62569718"
---
# <a name="combinepath-task"></a>CombinePath – úloha
Zkombinuje zadané cesty do jedné cesty.

## <a name="task-parameters"></a>Parametry úlohy
 Následující tabulka popisuje parametry [CombinePath – úloha](../msbuild/combinepath-task.md).

|Parametr|Popis|
|---------------|-----------------|
|`BasePath`|Vyžaduje `String` parametru.<br /><br /> Základní cesta ke sloučení s jiné cesty. Může být relativní cestu, absolutní cestu nebo prázdné.|
|`Paths`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Seznam jednotlivých cesty ke sloučení s BasePath k vytvoření kombinované cesty. Cesty může být relativní nebo absolutní.|
|`CombinedPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Kombinovanou cestu, který je vytvořen pomocí této úlohy.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)