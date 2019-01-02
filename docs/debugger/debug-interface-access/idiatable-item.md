---
title: Idiatable::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e8ba825c0dba1b0218e53f9ad66f6958602d0c2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53953976"
---
# <a name="idiatableitem"></a>IDiaTable::Item
Získá odkaz na zadané položce v tabulce.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [in] Index položky tabulky uvedeným v rozsahu 0 až `count`-1, kde `count` je vrácený [idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md)metody.  
  
 `element`  
 [out] Vrátí `IUnknown` objekt, který reprezentuje položku zadané tabulky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tabulka představuje kolekci objektů. V závislosti na tyto objekty parametr element přetypovat na odpovídající rozhraní. Například, pokud tabulka obsahuje [idiasegment –](../../debugger/debug-interface-access/idiasegment.md) objekty, pak parametr element může být převeden na `IDiaSegment` rozhraní.  
  
 To je běžnější přístup k volání `QueryInterface` metoda ve [idiatable –](../../debugger/debug-interface-access/idiatable.md) rozhraní pro příslušné enumerátor rozhraní a používat čítače výčtu specifické metody pro přístup k obsahu tabulky. Zobrazit [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) rozhraní pro příklad.  
  
## <a name="see-also"></a>Viz také  
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)   
 [Idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [Idiasegment –](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)