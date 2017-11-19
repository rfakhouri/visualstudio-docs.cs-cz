---
title: "Idiasession::symsareequiv – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 776e3868e8529657fb77cc9fac1d42eb04cdd722
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)