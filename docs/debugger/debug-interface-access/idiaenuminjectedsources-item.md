---
title: Idiaenuminjectedsources::Item – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 403632696091ecb3baa2550954fcfe0f3544bf15
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
Načte vložený zdroj prostřednictvím indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD                index,  
   IDiaInjectedSource** injectedSource  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [v] Z indexu [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) objekt, který má být načtena. Index je rozsahu od 0 do `count`-1, kde `count` je vrácený [idiaenuminjectedsources::get_count –](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) metoda.  
  
 injectedSource  
 [out] Vrátí [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) objekt reprezentující vložený zdroj.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)