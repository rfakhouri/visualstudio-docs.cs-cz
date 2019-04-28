---
title: Ijsdebugframe::getdocumentpositionwithid – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetDocumentPositionWithId
apilocation:
- jscript9diag.dll
ms.assetid: 48f8eb26-8ae4-4d5c-bd94-796023b03bcb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 741fe323e787c57f5f05a25461eae87c98dba70f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558135"
---
# <a name="ijsdebugframegetdocumentpositionwithid-method"></a>IJsDebugFrame::GetDocumentPositionWithId – metoda
Vrací aktuální pozici tohoto rámce zásobníku v rámci dokumentu uživatelské úrovni.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDocumentPositionWithId(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocumentId`  
 [out] Jedinečné ID pro zdrojový dokument (ukazatel na IDebugDocumentText).  
  
 `pCharacterOffset`  
 [out] Odsazení znaku od nuly od začátku skriptu.  
  
 `pStatementCharCount`  
 [out] Délka aktuálního příkazu, který začíná * pCharacterOffset, ve znacích.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugFrame – rozhraní](../../winscript/reference/ijsdebugframe-interface.md)