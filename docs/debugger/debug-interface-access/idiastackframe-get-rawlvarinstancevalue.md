---
title: Idiastackframe::get_rawlvarinstancevalue – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 66056d2f871d142da46cae25b2e9cb589836a580
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53838434"
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
Tato metoda načte hodnotu místní proměnné zadané jako nezpracovaný bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pInstance`  
 [in] `IDiaLVarInstance` Objekt představující instance má být získána hodnota pro lokální proměnné.  
  
 `cbDataMax`  
 [in] Maximální počet bajtů ve vyrovnávací paměti na které odkazuje `pbData`. To může být maximálně 8 bajtů (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] Vrátí skutečný počet bajtů uložených do vyrovnávací paměti.  
  
 `pbData`  
 [out] Vyrovnávací paměti, která vyplní data. IP adresa nesmí být `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)