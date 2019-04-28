---
title: Ijsdebugframe – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 5af46b18-9d25-4a23-b8d1-fa23bea3efcf
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57f5a848967148705a2b8dcd3f6b75dcb3a5db26
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558000"
---
# <a name="ijsdebugframe-interface"></a>IJsDebugFrame – metoda
Představuje rámec zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
IJsDebugFrame : public IUnknown;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[IJsDebugFrame::Evaluate – metoda](../../winscript/reference/ijsdebugframe-evaluate-method.md)|Vyhodnocení výrazu v kontextu tohoto rámce zásobníku.|  
|[IJsDebugFrame::GetDebugProperty – metoda](../../winscript/reference/ijsdebugframe-getdebugproperty-method.md)|Vrátí prohlížeč vlastnost pro tento rámec zásobníku.|  
|[IJsDebugFrame::GetDocumentPositionWithId – metoda](../../winscript/reference/ijsdebugframe-getdocumentpositionwithid-method.md)|Vrací aktuální pozici tohoto rámce zásobníku v rámci dokumentu uživatelské úrovni.|  
|[IJsDebugFrame::GetDocumentPositionWithName – metoda](../../winscript/reference/ijsdebugframe-getdocumentpositionwithname-method.md)|Vrací aktuální pozici tohoto rámce zásobníku v rámci dokumentu uživatelské úrovni.|  
|[IJsDebugFrame::GetName – metoda](../../winscript/reference/ijsdebugframe-getname-method.md)|Získá popisný název tohoto rámce zásobníku.|  
|[IJsDebugFrame::GetReturnAddress – metoda](../../winscript/reference/ijsdebugframe-getreturnaddress-method.md)|Získá zpáteční adresu posunutou na "start" (viz GetStackRange) rámečku.|  
|[IJsDebugFrame::GetStackRange – metoda](../../winscript/reference/ijsdebugframe-getstackrange-method.md)|Vrátí absolutní adresu rozsahu logického rámce zásobníku JavaScript.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)