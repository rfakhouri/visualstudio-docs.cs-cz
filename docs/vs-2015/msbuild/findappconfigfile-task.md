---
title: Findappconfigfile – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- FindAppConfigFile task [MSBuild]
- MSBuild, FindAppConfigFile task
ms.assetid: e292de3e-7482-4426-83ce-d921061808bf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fb9e1f3fbdc1a6f4d7c4e2c589f620f331a904ed
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59663177"
---
# <a name="findappconfigfile-task"></a>FindAppConfigFile – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vyhledá soubor app.config, pokud některý z zadaný seznamů.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `FindAppConfigFile` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AppConfigFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje první odpovídající položku v seznamu, pokud existuje.|  
|`PrimaryList`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje primární seznam prohledávat.|  
|`SecondaryList`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje seznam sekundární prohledávat.|  
|`TargetPath`|Vyžaduje `String` parametru.<br /><br /> Určuje hodnotu, chcete-li přidat jako metadata.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
