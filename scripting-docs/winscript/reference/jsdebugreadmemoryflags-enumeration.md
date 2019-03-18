---
title: Výčet JsDebugReadMemoryFlags | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JsDebugReadMemoryFlags
apilocation:
- jscript9diag.dll
ms.assetid: 0d98d154-9cb1-49de-b2df-a2d029d343b7
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c908fdbf17b13b84355dff208b7f3106bfc72087
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58156408"
---
# <a name="jsdebugreadmemoryflags-enumeration"></a>Výčet JsDebugReadMemoryFlags
Příznaky pro určení chování při čtení paměti  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
enum JsDebugReadMemoryFlags{   None = 0,   JsDebugAllowPartialRead= 0x1} JsDebugReadMemoryFlags;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`JsDebugAllowPartialRead`|Označuje, že volající vyžaduje úspěšné pouze pokud úspěšné čtení část paměti operace čtení. Pokud je nastaveno, bude vyvolána chyba E_JsDEBUG_INVALID_MEMORY_ADDRESS pouze pokud je "Adresa" neplatná. Pokud tento příznak není zaškrtnut, bude vyvolána chyba E_JsDEBUG_INVALID_MEMORY_ADDRESS, pokud libovolnou část požadované paměti nečitelná.|  
|`None`|Označuje, že volající vyžaduje výchozí chování pro ReadMemory.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)