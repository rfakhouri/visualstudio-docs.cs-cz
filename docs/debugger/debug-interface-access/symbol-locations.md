---
title: "Umístění symbolů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- LocationType values
- symbols [DIA SDK], locations
ms.assetid: 7c8cd8fe-169e-4161-9cff-5e9015984add
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd2ab3403fe01ce4ead0d3e388eaadbc34595675
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="symbol-locations"></a>Umístění symbolů
Většina symboly mít definovaný umístění v souboru bitové kopie. Umístění symbolu je zadán s hodnotou z [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md) výčtu. Symbol může podporovat další vlastnosti v závislosti na jeho umístění.  
  
 V následující tabulce jsou uvedeny nejčastěji používané typy umístění a jejich další vlastnosti.  
  
|Typ umístění|Další vlastnosti|  
|-------------------|---------------------------|  
|`LocIsNull`|žádná|  
|`LocIsStatic`|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)<br /><br /> [Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)<br /><br /> [Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md) (pokud jsou povolená relativní virtuálních adres)<br /><br /> [Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md) (Pokud je základní image byla nastavena na nenulové hodnoty)|  
|`LocIsTLS`|[Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)<br /><br /> [Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|  
|`LocIsRegRel`|[Idiasymbol::get_registerid –](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)<br /><br /> [Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocIsThisRel`|[Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocIsEnregistered`|[Idiasymbol::get_registerid –](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|  
|`LocIsBitField`|[Idiasymbol::get_bitposition –](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)<br /><br /> [Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)<br /><br /> [Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocIsSlot`|[Idiasymbol::get_slot –](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|  
|`LocIsIlRel`|[Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|  
|`LocInMetaData`|[Idiasymbol::get_token –](../../debugger/debug-interface-access/idiasymbol-get-token.md)|  
|`LocIsConstant`|[Idiasymbol::get_value –](../../debugger/debug-interface-access/idiasymbol-get-value.md)|  
  
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
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)