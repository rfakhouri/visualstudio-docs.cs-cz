---
title: Cppclean – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c833640958cefd2ac4f7e798ca3db09cc8819e8d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
|**FoldersToClean**|Požadované `String` parametr.<br /><br /> Určuje seznam oddělený středníkem adresářů pro čištění. Můžete zadat úplnou nebo relativní cestu a cesta může obsahovat zástupný znak (**\*\***).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)