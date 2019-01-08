---
title: Ijsdebugframe::getstackrange – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 049be8a665dae396d4e92fe847e757b266dc6025
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090282"
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