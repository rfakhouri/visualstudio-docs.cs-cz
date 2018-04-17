---
title: CombinePath – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 079c92e5f08deb414b612bf318e508b7adf50522
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="combinepath-task"></a>CombinePath – úloha
Spojuje do jednu cestu zadané cesty.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry [CombinePath – úloha](../msbuild/combinepath-task.md).  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`BasePath`|Požadované `String` parametr.<br /><br /> Základní cesta kombinovat s jiné cesty. Může být relativní cesty, absolutní cestu nebo prázdný.|  
|`Paths`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Seznam jednotlivé cesty kombinovat s BasePath k vytvoření kombinované cesta. Cesty může být relativní nebo absolutní.|  
|`CombinedPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Kombinovaná cesta, který je vytvořen pomocí této úlohy.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)