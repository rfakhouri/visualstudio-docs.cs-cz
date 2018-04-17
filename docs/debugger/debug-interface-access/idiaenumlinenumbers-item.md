---
title: Idiaenumlinenumbers::Item – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f4e65e8b5ec336d403ae9ec3f8a2c67c63e874d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
Načte číslo řádku prostřednictvím indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [v] Z indexu [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objekt, který má být načtena. Index je v rozsahu od 0 do `count`-1, kde `count` je vrácený [idiaenumlinenumbers::get_count –](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md) metoda.  
  
 lineNumber  
 [out] Vrátí [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objektu, který představuje číslo požadovaného řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)