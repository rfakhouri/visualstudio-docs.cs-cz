---
title: CombinePath – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3a7aba3111a799b650b7b3f7014d6d1a9f040b1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627907"
---
# <a name="combinepath-task"></a>CombinePath – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CombinePath – úloha](https://docs.microsoft.com/visualstudio/msbuild/combinepath-task).  
  
  
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
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



