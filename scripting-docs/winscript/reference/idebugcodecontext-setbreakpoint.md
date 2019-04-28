---
title: IDebugCodeContext::SetBreakPoint | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugCodeContext.SetBreakPoint
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugCodeContext::SetBreakPoint
ms.assetid: ecd42eae-66fa-40d3-9e47-08b826784108
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7bbfe38c1db9f7c9afff34f5a92b8c43b0f4f9ba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974524"
---
# <a name="idebugcodecontextsetbreakpoint"></a>IDebugCodeContext::SetBreakPoint
Zapne nebo vypne zarážku v tomto kontextu kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetBreakPoint(  
   BREAKPOINT_STATE  bps  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bps`  
 [in] Určuje stav zarážky pro tento kontext kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda Zapne nebo vypne zarážku v tomto kontextu kódu.  
  
## <a name="see-also"></a>Viz také  
 [Idebugcodecontext – rozhraní](../../winscript/reference/idebugcodecontext-interface.md)   
 [BREAKPOINT_STATE – výčet](../../winscript/reference/breakpoint-state-enumeration.md)