---
title: Cppclean – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a871effd2b7560cc34ae8e2a91c0b55f63bcfe44
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
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