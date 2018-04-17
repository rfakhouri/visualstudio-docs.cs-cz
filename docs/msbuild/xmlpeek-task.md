---
title: Xmlpeek – úloha | Microsoft Docs
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
- XmlPeek task [MSBuild]
- MSBuild, XmlPeek task
ms.assetid: 19196031-a3bc-41b5-9c4a-f2572630e179
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 76eefa66092320362c28034ae36fbd07ad198903
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="xmlpeek-task"></a>XmlPeek – úloha
Vrátí hodnoty podle specifikace dotaz XPath ze souboru XML.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `XmlPeek` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Namespaces`|Volitelné `String` parametr.<br /><br /> Určuje obor názvů pro předpony dotaz XPath.|  
|`Query`|Volitelné `String` parametr.<br /><br /> Určuje dotaz XPath.|  
|`Result`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje výsledky, které se vrátí pomocí této úlohy.|  
|`XmlContent`|Volitelné `String` parametr.<br /><br /> Určuje vstup XML jako řetězec.|  
|`XmlInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstup XML jako cestu k souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)