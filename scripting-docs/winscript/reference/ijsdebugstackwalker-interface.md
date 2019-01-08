---
title: Ijsdebugstackwalker – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 3fe30394-49c8-48e9-bde9-ffe5d79b2121
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d79950c6d5595a0a8a95623a7510c5523f16e41b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087892"
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