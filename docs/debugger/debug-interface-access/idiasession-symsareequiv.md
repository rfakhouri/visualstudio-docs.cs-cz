---
title: Idiasession::symsareequiv – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bfde8fec8ce399df765c911aa1ffaf292be1e50f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53893468"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
Kontroluje, jestli dva symboly jsou ekvivalentní.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `symbolA`  
 [in] První [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objektu při porovnání použit.  
  
 `symbolB`  
 [in] Druhá `IDiaSymbol` objektu při porovnání použit.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud jsou tyto symboly ekvivalentní, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`, symboly nejsou ekvivalentní. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)