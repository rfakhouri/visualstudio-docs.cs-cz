---
title: "Funcdebugstart – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- FuncDebugStart symbol
- debugging [DIA SDK], start point
ms.assetid: 1cbc6ca5-87d0-4c30-a39e-0a9dc62ce1a9
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b89d240980746a0a6a606bd43ff67f86e454bfdc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="funcdebugstart"></a>FuncDebugStart
Pokud funkci bod definované v ladění, která je začněte tím, že bodu je identifikována symbol s `SymTagFuncDebugStart` značky.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Posunutí součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Část součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_customcallingconvention –](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE`Pokud funkce, která používá vlastní konvence volání (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_farreturn –](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE`Pokud funkce provádí daleko návratový (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_interruptreturn –](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE`Pokud funkce obsahuje vrátit z přerušení (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_isstatic –](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE`Pokud funkce je označena jako statické (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol pro nadřazených funkce.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Počáteční body mají statické umístění; Podrobnosti najdete v tématu [umístění symbolu](../../debugger/debug-interface-access/symbol-locations.md).|  
|[Idiasymbol::get_noinline –](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE`Pokud zadaná funkce se [noinline](/cpp/cpp/noinline) atribut (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_noreturn –](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE`Pokud zadaná funkce se [noreturn](/cpp/cpp/noreturn) atribut (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_notreached –](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE`Pokud funkce je volána nikdy (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Posun symbolu v paměti Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md), `LocIsRegRel`.|  
|[Idiasymbol::get_optimizedcodedebuginfo –](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE`Pokud kód obsahuje informace o ladění optimalizovaného kódu (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Relativní pozici funkce v jeho bloku.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagFuncDebugStart` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Pozice funkce v rámci spustitelný soubor.|  
  
## <a name="see-also"></a>Viz také  
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)