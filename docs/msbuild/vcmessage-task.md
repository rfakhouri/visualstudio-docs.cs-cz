---
title: "Vcmessage – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.task.vcmessage
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- VCMessage task (MSBuild (Visual C++))
- MSBuild (Visual C++), VCMessage task
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8f3ec9c3b41d7ef8bffaa1dd1c607cd39610143b
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="vcmessage-task"></a>VCMessage – úloha
Protokoly upozornění a chybové zprávy v průběhu sestavení.  
  
## <a name="remarks"></a>Poznámky  
 Tato úloha pomáhá implementovat MSBuild pro Visual C++ a není určena k volání uživatelem. Další informace naleznete v tématu <xref:Microsoft.Build.Utilities.TaskLoggingHelper>.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **vcmessage –** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**Argumenty**|Volitelné **řetězec** parametr.<br /><br /> Seznam zpráv k zobrazení oddělených středníky.|  
|**Kód**|Požadované **řetězec** parametr.<br /><br /> Číslo chyby, která kvalifikují zprávy.|  
|**Typ**|Volitelné **řetězec** parametr.<br /><br /> Určuje typ zprávy pro vydávání. Zadejte buď `"Warning"` pro vydávání zprávu upozornění nebo `"Error"` pro vydávání chybovou zprávu.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)