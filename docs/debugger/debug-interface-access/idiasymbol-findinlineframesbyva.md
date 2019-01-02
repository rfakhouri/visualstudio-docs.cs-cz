---
title: IDiaSymbol::findInlineFramesByVA | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 54295d3e-bbb6-4c10-ab9d-adcfc22b1f71
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8bdf5fbc0ac282dbf6ccda9a5fc5931a9eb9ffdc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53874901"
---
# <a name="idiasymbolfindinlineframesbyva"></a>IDiaSymbol::findInlineFramesByVA
Načte výčet, který umožňuje klientovi iterovat přes všechny vložené rámce na zadanou virtuální adresu (VA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineFramesByVA (   
   ULONGLONG         va,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `va`  
 [in] Určuje adresu jako VA.  
  
 `ppResult`  
 [out] Obsahuje `IDiaEnumSymbols` objekt, který obsahuje seznam snímků, které jsou načteny.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)