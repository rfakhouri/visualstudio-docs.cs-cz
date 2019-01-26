---
title: IDiaSession::symsAreEquiv | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91a3081cc32eb4286ed7b981dfa2a070dbf4a0ff
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036690"
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