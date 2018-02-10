---
title: "Formaturl – úloha | Microsoft Docs"
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
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8b353984812b8ce586054771355f023d433312b3
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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