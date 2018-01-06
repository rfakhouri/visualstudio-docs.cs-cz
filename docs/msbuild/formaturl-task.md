---
title: "Formaturl – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3aa488a24646d9d3d3315efe5efca7dca53f68d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="formaturl-task"></a>FormatUrl – úloha
Převede adresu URL ve správném formátu adresy URL.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `FormatUrl` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`InputUrl`|Volitelné `String` parametr.<br /><br /> Určuje adresu URL k formátování.|  
|`OutputUrl`|Volitelné `String` výstupní parametr.<br /><br /> Určuje formátovaný adresu URL.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě nutnosti parametry, které jsou uvedené v tabulce tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)