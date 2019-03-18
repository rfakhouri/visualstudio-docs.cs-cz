---
title: Ijsdebugframe::evaluate – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: b328d6071ae9dc96b8e7f62bad6d4417aa1730f4
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157812"
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