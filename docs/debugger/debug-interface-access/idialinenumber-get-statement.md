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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c6b16d142f5bdc83b9a16e3299c15a0c845cf2c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949320"
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