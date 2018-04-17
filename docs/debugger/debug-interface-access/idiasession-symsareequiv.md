---
title: Idiasession::symsareequiv – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 41e9663999639b45995caa28dbc08ce194febdcb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
Kontroluje, zda jsou dva symboly ekvivalentní.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `symbolA`  
 [v] První [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt porovnání.  
  
 `symbolB`  
 [v] Druhý `IDiaSymbol` objekt porovnání.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud odpovídají symboly, vrátí `S_OK`, jinak vrátí `S_FALSE`, nejsou ekvivalentní symboly. Jinak je vrácen kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)