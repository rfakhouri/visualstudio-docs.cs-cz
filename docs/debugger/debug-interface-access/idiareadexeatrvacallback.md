---
title: Idiareadexeatrvacallback – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e00ce2e1286c2309a11984f9bde23aa74071a076
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859289"
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
Umožňuje klientské aplikaci slouží k poskytování bajtů spustitelný soubor určený relativní virtuální adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaReadExeAtRVACallback`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|Přečte zadaný počet bajtů počínaje zadanou relativní virtuální adresu (RVA) ze spustitelného souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Klientská aplikace implementuje toto rozhraní negace bajtů se spustitelný soubor používající relativní virtuální adresu do souboru ke spustitelnému souboru. Chcete-li použít absolutní posun, implementovat [idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Tato metoda je implementované klientská aplikace a předat [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody jako alternativní metoda pro čtení souboru.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)