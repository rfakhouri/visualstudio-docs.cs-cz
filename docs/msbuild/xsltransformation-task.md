---
title: "Xsltransformation – úloha | Microsoft Docs"
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
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4eb192777b85adbfc270c7cbdb4469548333c5ec
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="xsltransformation-task"></a>XslTransformation – úloha
Transformace na XML vstup pomocí transformaci XSLT nebo zkompilovat XSLT a výstupy do výstupní zařízení nebo souboru.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `XslTransformation` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`OutputPaths`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje výstupní soubory pro transformaci XML.|  
|`Parameters`|Volitelné `String` parametr.<br /><br /> Určuje parametry, které XSLT vstup dokumentu.|  
|`XmlContent`|Volitelné `String` parametr.<br /><br /> Určuje vstup XML jako řetězec.|  
|`XmlInputPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje vstupní soubory XML.|  
|`XslCompiledDllPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje kompilované XSLT.|  
|`XslContent`|Volitelné `String` parametr.<br /><br /> Určuje vstup XSLT jako řetězec.|  
|`XslInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstupní soubor XSLT.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)