---
title: IDiaSymbol::getSrcLineOnTypeDefn | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ad554d18-9988-4b64-ad71-e7594c266e94
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e242be35a11971c1d0c045c904fc7ed545cfc6f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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