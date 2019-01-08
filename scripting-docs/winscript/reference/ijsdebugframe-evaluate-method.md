---
title: Ijsdebugframe::evaluate – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.Evaluate
apilocation:
- jscript9diag.dll
ms.assetid: 0ee61340-37b8-4fbb-a028-748b5315e279
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 574af7823add67a00fc8add922b5e352fa1b369c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091920"
---
# <a name="ijsdebugframeevaluate-method"></a>IJsDebugFrame::Evaluate – metoda
Vyhodnocení výrazu v kontextu tohoto rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Evaluate(  
   LPCOLESTR pExpressionText,  
   IJsDebugProperty **ppDebugProperty,  
   BSTR *pError  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pExpressionText`  
 [in] Výraz k vyhodnocení.  
  
 `ppDebugProperty`  
 [out] Objekt reprezentující vlastnost prohlížeče.  
  
 `pError`  
 [out] Chybová zpráva, pokud dojde k chybě.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Vrátí následující: S_OK: Hodnocení úspěšné, * ppDebugProperty obsahuje výsledek hodnocení. S_FALSE: Hodnocení vyvolá chybu (nebo operace hodnocení není podporována) \*pError obsahuje chybovou zprávu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugFrame – rozhraní](../../winscript/reference/ijsdebugframe-interface.md)