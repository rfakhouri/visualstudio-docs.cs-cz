---
title: IDiaSymbol::getSrcLineOnTypeDefn | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ad554d18-9988-4b64-ad71-e7594c266e94
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 673af188dd8a0b5f51de5c2148d57b97358a7f58
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetsrclineontypedefn"></a>IDiaSymbol::getSrcLineOnTypeDefn
Načte zdrojového souboru a řádku číslo, které označuje, kde je definován na zadaný typ definovaný uživatelem.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT getSrcLineOnTypeDefn(  
   IDiaLineNumber **ppResult);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppResult`  
 [out] A `IDiaLineNumber` objekt, který obsahuje zdrojový soubor a řádku číslo kde definované uživatelem.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)