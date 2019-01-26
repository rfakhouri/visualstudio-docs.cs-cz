---
title: Idiaenuminjectedsources::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d258e2c1ba71ab294435f2437c7b6dc3de75cfb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54925783"
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
Načte vložený zdroj pomocí indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD                index,  
   IDiaInjectedSource** injectedSource  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [in] Index o [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) objekt, který se má načíst. Index je rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenuminjectedsources::get_count –](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) metody.  
  
 injectedSource  
 [out] Vrátí [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) objekt představující vložené zdroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)