---
title: IDiaSymbol::findInlineeLines | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 56ba4bc0-8f96-47c2-8b18-332b4e7c2d91
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 008328536e7fe465594f4fbfec25a52aa2a1ed64
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53927074"
---
# <a name="idiasymbolfindinlineelines"></a>IDiaSymbol::findInlineeLines
Načte výčet, který umožňuje klientovi k iteraci v rámci informace čísla řádku všech funkcí, které jsou vloženy, přímo nebo nepřímo v tento symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineeLines (   
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppResult`  
 [out] Obsahuje `IDiaEnumLineNumbers` objekt, který obsahuje seznam čísel řádků, které jsou načteny.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession::findInlineeLines](../../debugger/debug-interface-access/idiasession-findinlineelines.md)