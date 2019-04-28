---
title: Ijsdebugframe::getstackrange – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetStackRange
apilocation:
- jscript9diag.dll
ms.assetid: a6d1d8be-efc0-442d-9756-1959c8f102bd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 52dd6114d3ec462f91f8bce5e76f73c5487746ed
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558213"
---
# <a name="ijsdebugframegetstackrange-method"></a>IJsDebugFrame::GetStackRange – metoda
Vrátí absolutní adresu rozsahu logického rámce zásobníku JavaScript.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetStackRange(  
   UINT64 *pStart,  
   UINT64 *pEnd  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStart`  
 [out] Nejspodnější ukazatel zásobníku rámce.  
  
 `pEnd`  
 [out] TOP nejhornější ukazatel zásobníku rámce.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je užitečná pro piecing společně trasování zásobníků shromážděných z více modulů – runtime. Počáteční a koncový ukazatel zásobníku může zahrnovat více rámců zásobníku fyzického počítače (pro interpretované snímky modulu runtime jazyka JavaScript). Start > konec se vzrůstajícím zásobníkem z vysoké na nízkou adresu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugFrame – rozhraní](../../winscript/reference/ijsdebugframe-interface.md)