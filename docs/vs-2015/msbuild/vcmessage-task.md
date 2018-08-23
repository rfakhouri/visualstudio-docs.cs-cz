---
title: Vcmessage – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d667c53e00e7b92d133c260b5c3cc471a64f355b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669237"
---
# <a name="vcmessage-task"></a>VCMessage – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vcmessage – úloha](https://docs.microsoft.com/visualstudio/msbuild/vcmessage-task).  
  
  
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



