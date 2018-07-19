---
title: Cppclean – úloha | Dokumentace Microsoftu
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
ms.openlocfilehash: fc66d09b16c62765848a77ea4fd4a2d9f65ad418
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2018
ms.locfileid: "37946534"
---
# <a name="cppclean-task"></a>CPPClean – úloha
Odstraní dočasné soubory, které MSBuild vytvoří při vytváření projektu Visual C++. Proces odstraňování souborů sestavení se označuje jako *čištění*.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **cppclean –** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**DeletedFiles**|Volitelné `ITaskItem[]` výstupní parametr.<br /><br /> Definuje pole objektů MSBuild výstupní soubor položky, které lze používat a, protože ho vygeneroval úlohy.|  
|**DoDelete**|Volitelné **logická** parametru.<br /><br /> Pokud `true`, čištění dočasné soubory sestavení.|  
|**FilePatternsToDeleteOnClean**|Vyžaduje `String` parametru.<br /><br /> Určuje středníky oddělený seznam přípon souborů souborů k vyčištění.|  
|**FilesExcludedFromClean**|Volitelné `String` parametru.<br /><br /> Určuje středníky oddělený seznam souborů nechcete vyčistit.|  
|**FoldersToClean**|Vyžaduje `String` parametru.<br /><br /> Určuje středníky oddělený seznam adresářů pro vyčištění. Můžete zadat úplnou nebo relativní cestu a cesta může obsahovat zástupný znak (**\*\***).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)