---
title: IDiaSession::findInlineeLinesByVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: dffe6594-e0d1-4ed5-aeea-8773f88d82a6
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0309dfd4f14ed7bdb049cdb0bde16a038bb78e37
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindinlineelinesbyva"></a>IDiaSession::findInlineeLinesByVA
Načte výčet, který umožňuje klientům k iteraci v rámci informace číslo řádku všech funkcí, které jsou vložená, přímo nebo nepřímo, podle symbol zadaný nadřazený a jsou obsaženy v rámci zadané virtuální adresy (VA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           parent,   ULONGLONG             va,   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [v] `IDiaSymbol` Představující nadřazený objekt.  
  
 `va`  
 [v] Určuje adresu jako VA.  
  
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