---
title: "Cppclean – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.task.cppclean
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CPPClean task
- CPPClean task (MSBuild (Visual C++))
ms.assetid: b62a482e-8fb5-4999-b50b-6605a078e291
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 37f976d54e3a18d3bc854b46678f79ecec41659f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="cppclean-task"></a>CPPClean – úloha
Odstraní dočasné soubory, které MSBuild vytvoří při sestavení projektu Visual C++. Proces odstraňování souborů sestavení se označuje jako *čištění*.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **cppclean –** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**DeletedFiles**|Volitelné `ITaskItem[]` výstupní parametr.<br /><br /> Definuje pole MSBuild výstupní soubor položek, které je možné využívat a vygenerované úlohami.|  
|**DoDelete**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, Vyčistit dočasné soubory sestavení.|  
|**FilePatternsToDeleteOnClean**|Požadované `String` parametr.<br /><br /> Určuje seznam přípon souborů pro čištění oddělených středníky.|  
|**FilesExcludedFromClean**|Volitelné `String` parametr.<br /><br /> Určuje seznam souborů nechcete vyčistit oddělených středníky.|  
|**FoldersToClean**|Požadované `String` parametr.<br /><br /> Určuje seznam oddělený středníkem adresářů pro čištění. Můžete zadat úplnou nebo relativní cestu a cesta může obsahovat zástupný znak (**\***).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)