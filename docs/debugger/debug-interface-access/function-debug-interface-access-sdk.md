---
title: "Funkce (přístup k rozhraní ladění SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Function symbol
ms.assetid: 458dc91c-b78b-4427-84f4-615d89e26760
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39d3871fcfbd3702e2ad198f2061be41dc51ac18
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="function-debug-interface-access-sdk"></a>Funkce (Přístup k rozhraní ladění SDK)
Jednotlivé funkce je identifikovaná `SymTagFunction` symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|`Data type`|Popis|  
|--------------|-----------------|-----------------|  
|[Idiasymbol::get_access –](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Jedna z hodnot [CV_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md), pokud funkci členské funkce.|  
|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Posunutí součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Část součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbol pro třídu, pokud je funkce členské funkce|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud funkce je označena jako konstanta.|  
|[Idiasymbol::get_customcallingconvention –](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE`Pokud funkce, která používá vlastní konvence volání (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_farreturn –](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE`Pokud funkce provádí daleko návratový (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_hasalloca –](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|`BOOL`|`TRUE`Pokud funkce, která používá funkce přidělenou paměť (pouze uinnder DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_haseh –](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|`BOOL`|`TRUE`Pokud funkce obsahuje výjimky C++ stylu zpracování (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_haseha –](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|`BOOL`|`TRUE`Pokud funkce obsahuje zpracování asynchronní výjimek (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_hasinlasm –](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|`BOOL`|`TRUE`Pokud funkce obsahuje vložené sestavení (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_haslongjump –](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|`BOOL`|`TRUE`Pokud obsahuje funkce [longjmp](/cpp/c-runtime-library/reference/longjmp) volání (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_hassecuritychecks –](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE`Pokud funkce obsahuje kontrol zabezpečení (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_hasseh –](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|`BOOL`|`TRUE`Pokud funkce obsahuje výjimky Win32 stylu strukturovaná zpracování (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_hassetjump –](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|`BOOL`|`TRUE`Pokud obsahuje funkce [setjmp](/cpp/c-runtime-library/reference/setjmp) volání (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_interruptreturn –](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE`Pokud funkce má vrátit z přerušení (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_intro –](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|`TRUE`Pokud je funkce Úvod virtuální.|  
|[Idiasymbol::get_inlspec –](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|`BOOL`|`TRUE`Pokud byl označen funkci s jedním z [vložené, __inline, \__forceinline](/cpp/cpp/inline-functions-cpp.md) atributy.|  
|[Idiasymbol::get_isnaked –](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|`BOOL`|`TRUE`Pokud je označené jako funkci [holé](/cpp/cpp/naked-cpp) atribut (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_isstatic –](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE`Pokud funkce není statický (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Počet bajtů funkce kódu, od umístění.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol nadřazených kompilace.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Funkce mohou mít statické nebo metadata umístění; Podrobnosti najdete v tématu [umístění symbolu](../../debugger/debug-interface-access/symbol-locations.md).|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název funkce.|  
|[Idiasymbol::get_noinline –](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE`Pokud funkce není vložená funkce (pouze n do V8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_notreached –](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE`Pokud funkce není dostupná (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_noreturn –](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE`Pokud funkce nevrátí hodnotu (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_nostackordering –](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|`BOOL`|`TRUE`Pokud funkci bylo kompilováno s kontrola zabezpečení vyrovnávací paměti, ale žádné řazení zásobníku může provést.|  
|[Idiasymbol::get_optimizedcodedebuginfo –](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE`Pokud kód obsahuje informace o ladění optimalizovaného kódu (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_pure –](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|`TRUE`Pokud je funkce čistý virtuální.|  
|[Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Tato funkce v rámci jeho modul relativní umístění.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagFunction` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_token –](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|Metadata token pro funkci.|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro podpis funkce.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu.|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud je funkce nezarovnané.|  
|[Idiasymbol::get_undecoratedname –](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|`BSTR`|Bez upraveného formu název funkce (pouze v v8.0 DIA SDK nebo novější)|  
|[Idiasymbol::get_undecoratednameex –](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|`BSTR`|Část nebo všechny upraveného formu název funkce (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_virtual –](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE`Pokud virtuální funkce.|  
|[Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Pozice této funkce v rámci spustitelné bitové kopie.|  
|[Idiasymbol::get_virtualbaseoffset –](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|Pokud virtuální funkci, pak posun v tabulce virtuální funkce.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud funkce je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [CV_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md)   
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)