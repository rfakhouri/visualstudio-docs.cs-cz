---
title: Errorresumeaction – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ERRORRESUMEACTION
apilocation:
- scrobj.dll
helpviewer_keywords:
- ERRORRESUMEACTION enumeration
ms.assetid: a68293c8-056b-439f-83e7-69e4a38f4976
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d92b4b2e00b25a509d29511008876d781c8a577a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955170"
---
# <a name="errorresumeaction-enumeration"></a>Výčet ERRORRESUMEACTION
Popisuje, jak pokračovat od chyby za běhu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagERRORRESUMEACTION {  
   ERRORRESUMEACTION_ReexecuteErrorStatement,  
   ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller,  
   ERRORRESUMEACTION_SkipErrorStatement,  
} ERRORRESUMEACTION;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|ERRORRESUMEACTION_ReexecuteErrorStatement|Znovu spustí příkaz, který vytvořil chybu.|  
|ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller|Umožňuje modulu jazyka chybu zpracovat.|  
|ERRORRESUMEACTION_SkipErrorStatement|Pokračuje v provádění kódu, příkazem, který vytvořil chybu.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)