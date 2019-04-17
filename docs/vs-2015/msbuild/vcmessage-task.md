---
title: Vcmessage – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 508d1fe33046f6051c9c5c1b8e54036e78ae7d2f
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59652368"
---
# <a name="vcmessage-task"></a>VCMessage – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Protokoly upozornění a chybové zprávy během sestavení.  
  
## <a name="remarks"></a>Poznámky  
 Tato úloha pomáhá implementovat MSBuild pro Visual C++ a není určena k volání uživatelem. Další informace naleznete v tématu <xref:Microsoft.Build.Utilities.TaskLoggingHelper>.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **vcmessage –** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**Argumenty**|Volitelné **řetězec** parametru.<br /><br /> Středníkem oddělený seznam zpráv k zobrazení.|  
|**Kód**|Vyžaduje **řetězec** parametru.<br /><br /> Číslo chyby, která kvalifikuje zprávy.|  
|**Typ**|Volitelné **řetězec** parametru.<br /><br /> Určuje typ zprávy a vygenerovat. Zadejte buď `"Warning"` vygenerovat upozornění, nebo `"Error"` generovat chybovou zprávu.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
