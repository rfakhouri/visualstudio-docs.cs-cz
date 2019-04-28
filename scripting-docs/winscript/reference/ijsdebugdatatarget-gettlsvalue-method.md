---
title: Ijsdebugdatatarget::gettlsvalue – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.GetTlsValue
apilocation:
- jscript9diag.dll
ms.assetid: db575be9-7b24-45c5-9008-e4f2f76d6757
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 458aaab05f274983fdaf69c6e702502974665403
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62582807"
---
# <a name="ijsdebugdatatargetgettlsvalue-method"></a>IJsDebugDataTarget::GetTlsValue – metoda
Pro vlákno, který se právě ladí načte hodnotu ve slotu vlákno místní úložiště (TLS) pro zadaný index TLS.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetTlsValue(  
   DWORD threadId,  
   UINT32 tlsIndex,  
   UINT64 *pValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `threadId`  
 [in] Vlákno spuštěné v cílovém procesu pro čtení z.  
  
 `tlsIndex`  
 [in] Protokol TLS index, který byl přiřazen, když Cílový proces volal funkci TlsAlloc.  
  
 `pValue`  
 [out] Hodnota velikosti ukazatele, která byla uložena v patici TLS vlákna. Pokud je cílové vlákno 32bitové, horní 32 bitové této hodnoty bude nula.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Každý podproces procesu má vlastní pozici pro každý protokol TLS index.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)