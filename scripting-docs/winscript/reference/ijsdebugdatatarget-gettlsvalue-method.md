---
title: Ijsdebugdatatarget::gettlsvalue – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 8f81e9ea6cca9bf54753a496e07903d23bb913fc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095326"
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