---
title: Ijsdebugstackwalker – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 3fe30394-49c8-48e9-bde9-ffe5d79b2121
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d06af2c509339d9499f66e1f267c54c69951e225
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150891"
---
# <a name="ijsdebugstackwalker-interface"></a>IJsDebugStackWalker – rozhraní
Představuje zásobník pro zadaný podproces.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
IJsDebugStackWalker : public IUnknown;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[IJsDebugStackWalker::GetNext – metoda](../../winscript/reference/ijsdebugstackwalker-getnext-method.md)|Získá další snímek.|  
  
## <a name="remarks"></a>Poznámky  
 Zásobníky lze vytvořit pouze zatímco je cíl zastaven a jsou neplatné, jakmile opět pokračujete cílovém procesu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)