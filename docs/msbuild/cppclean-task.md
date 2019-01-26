---
title: Cppclean – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: faf3650bdc190f498d981db5a0cd50867e86cdba
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934875"
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
|**FoldersToClean**|Vyžaduje `String` parametru.<br /><br /> Určuje středníky oddělený seznam adresářů pro vyčištění. Můžete zadat úplnou nebo relativní cestu a cestu může obsahovat zástupný znak (*).|  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)