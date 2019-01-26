---
title: Idialinenumber::get_statement – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_statement method
ms.assetid: 22b8ee29-79ef-427f-bd05-00d255ab836b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e517eac8e3649328c56b77e86288fbb9a52ba436
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54977431"
---
# <a name="idialinenumbergetstatement"></a>IDiaLineNumber::get_statement
Získá příznak označující, že informace o tomto řádku popisuje začátku příkazu namísto výrazu, ve zdrojovém programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_statement (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` Pokud informace o tomto řádku popisuje počátku příkazu ve zdrojovém programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Příkazy může zahrnovat více řádků. Tato metoda znamená, pokud přidružený řádek číslo označuje začátek Víceřádkový příkazu.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)