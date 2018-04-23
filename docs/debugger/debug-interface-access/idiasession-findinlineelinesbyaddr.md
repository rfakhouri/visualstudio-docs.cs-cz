---
title: IDiaSession::findInlineeLinesByAddr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bb70e408-eed1-4c9c-b5b1-44323125f48b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 139bc3c9291650b5e3e991324dbf8c560078c2de
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionfindinlineelinesbyaddr"></a>IDiaSession::findInlineeLinesByAddr
Načte výčet, který umožňuje klientům k iteraci v rámci informace číslo řádku všech funkcí, které jsou vložená, přímo nebo nepřímo, podle symbol zadaný nadřazený a jsou obsaženy v rámci zadaný rozsah adres.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineeLinesByAddr (   
   IDiaSymbol*           parent,   DWORD                 isect,   DWORD                 offset,   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [v] `IDiaSymbol` Představující nadřazený objekt.  
  
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
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)