---
title: Výčet JS_PROPERTY_MEMBERS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JS_PROPERTY_MEMBERS
apilocation:
- jscript9diag.dll
ms.assetid: 3b870e5c-5518-4073-8384-f0c9c1777d9e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 597764d1e55b895c30e2b00981a7a1be53e16022
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968656"
---
# <a name="jspropertymembers-enumeration"></a>Výčet JS_PROPERTY_MEMBERS
Příznaky pro určení typu informací, které mají být vráceny v žádosti o členy objektu  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
enum JS_PROPERTY_MEMBERS{   JS_PROPERTY_MEMBERS_ALL = 0,   JS_PROPERTY_MEMBERS_ARGUMENTS = 1} JS_PROPERTY_MEMBERS;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`JS_PROPERTY_MEMBERS_ALL`|Představuje žádost o vytvoření výčtu všech členů.|  
|`JS_PROPERTY_MEMBERS_ARGUMENTS`|Představuje žádost o výčet pouze argumenty.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)