---
title: Struktura JsDebugPropertyInfo | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JsDebugPropertyInfo
apilocation:
- jscript9diag.dll
ms.assetid: 3a5463a7-2013-4846-9ab2-8beb675a5a6a
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8aeb2dcfc116c8c735cda95fc9d7ab9da97cab3b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58154566"
---
# <a name="jsdebugpropertyinfo-structure"></a>Struktura JsDebugPropertyInfo
Označuje informace o vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct tagJsDebugPropertyInfo{   BSTR name;   BSTR type;   BSTR value;   BSTR fullName;   JS_PROPERTY_ATTRIBUTES attr;} JsDebugPropertyInfo;  
```  
  
## <a name="members"></a>Členové  
 `name`  
 Název vlastnosti  
  
 `type`  
 Typ vlastnosti.  
  
 `value`  
 Hodnota vlastnosti  
  
 `fullName`  
 Celý název vlastnosti.  
  
 `attr`  
 Výčet, který představuje atributy vlastnosti.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)