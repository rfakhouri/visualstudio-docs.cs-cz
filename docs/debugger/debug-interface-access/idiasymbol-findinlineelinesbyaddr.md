---
title: IDiaSymbol::findInlineeLinesByAddr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f1ab47ca-c851-48ea-9c12-47fb80b31102
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f714e42156cb4f7889cae52b8a5968a1a7d71f4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolfindinlineelinesbyaddr"></a>IDiaSymbol::findInlineeLinesByAddr
Načte výčet, který umožňuje klientům k iteraci v rámci řádku informace o čísle všech funkcí, které jsou vložená, přímo ani nepřímo, v tento symbol v rámci zadaný rozsah adres.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineeLinesByAddr (   
   DWORD                 isect,  
   DWORD                 offset,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `isect`  
 [v] Určuje komponentu část adresy.  
  
 `offset`  
 [v] Určuje posunutí součást adresy.  
  
 `length`  
 [v] Určuje rozsah adres v počet bajtů, tak, aby pokrývalo k tomuto dotazu.  
  
 `ppResult`  
 [out] Obsahuje `IDiaEnumLineNumbers` objekt, který obsahuje seznam čísla řádků, která jsou načtena.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession::findInlineeLines](../../debugger/debug-interface-access/idiasession-findinlineelines.md)