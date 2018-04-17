---
title: Formaturl – úloha | Microsoft Docs
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
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e14c00820363c79383a445d6a632a0e7b6602c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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