---
title: "Xmlpoke – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3b189fbaa7cb03b8a20f67c0f57d19fa9c304c1b
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="xmlpoke-task"></a>XmlPoke – úloha
Nastaví hodnoty podle specifikace dotaz XPath do souboru XML.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `XmlPoke` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Namespaces`|Volitelné `String` parametr.<br /><br /> Určuje obor názvů pro předpony dotaz XPath.|  
|`Query`|Volitelné `String` parametr.<br /><br /> Určuje dotaz XPath.|  
|`Value`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje výstupní soubor.|  
|`XmlInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstup XML jako cestu k souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)