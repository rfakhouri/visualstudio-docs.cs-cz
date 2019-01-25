---
title: Xsltransformation – úloha | Dokumentace Microsoftu
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
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 892ecb7f97be3d89a0f6e8104b0b55647a6fe63e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54793129"
---
# <a name="xsltransformation-task"></a>XslTransformation – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
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
