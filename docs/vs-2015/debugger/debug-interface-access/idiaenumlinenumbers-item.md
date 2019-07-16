---
title: Idiaenumlinenumbers::Item – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 630c86e463cdc6ff838fad00d5d02e6f67c729d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190133"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Získá číslo řádku pomocí indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [in] Index o [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objekt, který se má načíst. Index je v rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenumlinenumbers::get_count –](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md) metody.  
  
 Číslo řádku  
 [out] Vrátí [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objekt reprezentující počet požadovaných řádků.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
