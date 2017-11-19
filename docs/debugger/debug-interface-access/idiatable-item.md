---
title: "Idiatable::Item – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5c0c810dfd1a17f2fa63e64bf199a5882174aae
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiatableitem"></a>IDiaTable::Item
Získá odkaz na zadaný záznam v tabulce.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [v] Index položky tabulky v rozsahu od 0 do `count`-1, kde `count` je vrácený [idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md)metoda.  
  
 `element`  
 [out] Vrátí `IUnknown` objekt, který reprezentuje položku zadané tabulky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tabulka představuje kolekci objektů. V závislosti na tyto objekty lze převést parametr element na odpovídající rozhraní. Například, pokud tabulka obsahuje [idiasegment –](../../debugger/debug-interface-access/idiasegment.md) objekty, pak může být parametr element převeden `IDiaSegment` rozhraní.  
  
 Je více společný přístup k volání `QueryInterface` metoda v [idiatable –](../../debugger/debug-interface-access/idiatable.md) rozhraní pro rozhraní odpovídající enumerátor a používat konkrétní metody enumerátor pro přístup k obsahu tabulky. Najdete v článku [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) rozhraní pro příklad.  
  
## <a name="see-also"></a>Viz také  
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)   
 [Idiatable::get_count –](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [Idiasegment –](../../debugger/debug-interface-access/idiasegment.md)   
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)