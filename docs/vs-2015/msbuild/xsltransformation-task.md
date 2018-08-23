---
title: Xsltransformation – úloha | Dokumentace Microsoftu
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
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66ba37f75267e069ede64a25ac4c56bca8a4e8c5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672804"
---
# <a name="xsltransformation-task"></a>XslTransformation – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [xsltransformation – úloha](https://docs.microsoft.com/visualstudio/msbuild/xsltransformation-task).  
  
  
Transformace na XML vstup pomocí XSLT nebo kompilované XSLT a výstupů na zařízení s výstupní soubor nebo soubor.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `XslTransformation` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`OutputPaths`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje výstupní soubory transformace XML.|  
|`Parameters`|Volitelné `String` parametru.<br /><br /> Určuje parametry XSLT vstupní dokument.|  
|`XmlContent`|Volitelné `String` parametru.<br /><br /> Určuje vstup XML jako řetězec.|  
|`XmlInputPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje vstupní soubor XML.|  
|`XslCompiledDllPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje kompilované XSLT.|  
|`XslContent`|Volitelné `String` parametru.<br /><br /> Určuje vstup XSLT jako řetězec.|  
|`XslInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje vstupní soubor XSLT.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



