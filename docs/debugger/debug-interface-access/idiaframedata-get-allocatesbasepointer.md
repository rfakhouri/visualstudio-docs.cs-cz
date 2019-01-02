---
title: Idiaframedata::get_allocatesbasepointer – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_allocatesBasePointer method
ms.assetid: 8a33db5d-008c-4fe5-b64f-210c9b77f686
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3ce39d0fb64cdd89139bb4506c9b95719a3f172
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53951314"
---
# <a name="idiaframedatagetallocatesbasepointer"></a>IDiaFrameData::get_allocatesBasePointer
Získá příznak, který označuje, zda je základní ukazatel přidělen pro kód v tomto rozsahu adres. Tato metoda je zastaralá.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_allocatesBasePointer (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` Pokud je základní ukazatel přidělen; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost by měly být používány pouze kód, který dřív přístupné FPO_DATA nebo když program řetězec vrácený [idiaframedata::get_program –](../../debugger/debug-interface-access/idiaframedata-get-program.md) je metoda `NULL`. V opačném případě program řetězec obsahuje všechny informace potřebné k výpočtu předchozí hodnoty registru.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)