---
title: Symbol umístění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- LocationType values
- symbols [DIA SDK], locations
ms.assetid: 7c8cd8fe-169e-4161-9cff-5e9015984add
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 892c9f3b200466b22d847063ce2a60cf63301e5a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915072"
---
# <a name="symbol-locations"></a>Umístění symbolů
Většina symboly mít definované umístění v rámci souboru obrázku. Umístění symbolu je zadaný s hodnotou od [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) výčtu. Symbol může podporovat další vlastnosti v závislosti na jeho umístění.  
  
 V následující tabulce jsou uvedeny nejčastěji používané typy umístění a jejich další vlastnosti.  
  
|Typ umístění|Další vlastnosti|  
|-------------------|---------------------------|  
|`LocIsNull`|žádná|  
|`LocIsStatic`|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)<br /><br /> [IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)<br /><br /> [Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md) (pokud jsou povolené relativních virtuálních adres)<br /><br /> [Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md) (Pokud je základní image nastavený na nenulovou hodnotu)|  
|`LocIsTLS`|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)<br /><br /> [IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|  
|`LocIsRegRel`|[IDiaSymbol::get_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)<br /><br /> [IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocIsThisRel`|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocIsEnregistered`|[IDiaSymbol::get_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|  
|`LocIsBitField`|[IDiaSymbol::get_bitPosition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)<br /><br /> [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)<br /><br /> [IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocIsSlot`|[IDiaSymbol::get_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|  
|`LocIsIlRel`|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocInMetaData`|[IDiaSymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|  
|`LocIsConstant`|[IDiaSymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)   
 [Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)   
 [Idiasymbol::get_bitposition –](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)   
 [Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)   
 [Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)   
 [Idiasymbol::get_registerid –](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)   
 [Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)   
 [Idiasymbol::get_slot –](../../debugger/debug-interface-access/idiasymbol-get-slot.md)   
 [Idiasymbol::get_token –](../../debugger/debug-interface-access/idiasymbol-get-token.md)   
 [Idiasymbol::get_value –](../../debugger/debug-interface-access/idiasymbol-get-value.md)   
 [Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)   
 [Locationtype – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)