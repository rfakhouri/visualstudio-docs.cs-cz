---
title: Ienumjsstackframes::Next – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumJsStackFrames.Next
apilocation:
- jscript9diag.dll
ms.assetid: efceb3a1-9239-4f55-9cbb-94670679988b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94e3f478654fadec152aba0690a5474ebbfe02f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963296"
---
# <a name="ienumjsstackframesnext-method"></a>IEnumJsStackFrames::Next – metoda
Získá určený počet snímků.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Next(  
   ULONG cFrameCount,  
   JS_NATIVE_FRAME *pFrames,  
   ULONG *pcFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cFrameCount`  
 [in] Počet rámečků k získání.  
  
 `pFrames`  
 [out] Pole pro ukládání snímků.  
  
 `pcFetched`  
 [out] Počet vrácených snímků.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IEnumJsStackFrames – rozhraní](../../winscript/reference/ienumjsstackframes-interface.md)