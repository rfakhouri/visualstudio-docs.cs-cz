---
title: "Data (přístup k rozhraní SDK ladění) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- global variables [C++], as symbols
- local variables [C++], as symbols
- class members [C++], as symbols
- Data symbol
ms.assetid: 0f17e96a-2e06-42c9-a877-3e5e670ee0ef
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea233e8bf26b3bbb9dd7b1e962e3729e172b5a7e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="data-debug-interface-access-sdk"></a>Data (Přístup k rozhraní ladění SDK)
Všechny proměnné, jako je například parametry, místní proměnné, globální proměnné a členy třídy, jsou identifikovány `SymTagData` symboly. Konstantní hodnoty (`LocIsConstant`) se také identifikují s tímto typem.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_access –](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Pokud pole, pak jedna z hodnot [CV_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md).|  
|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Posunutí součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Část součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresstaken –](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|`BOOL`|`TRUE`Pokud tato data adresu odkazuje jiný symbol.|  
|[Idiasymbol::get_bitposition –](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|`DWORD`|Bit pozici umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md) (nepodporované ve v8.0 DIA SDK).|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbol pro třídu, pokud je to struktury, sjednocení nebo pole třídy.|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_compilergenerated –](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|`BOOL`|`TRUE`Pokud data vygenerovalo kompilátoru.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud data je označen jako konstanta.|  
|[Idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|Jeden z [DataKind – výčet](../../debugger/debug-interface-access/datakind.md) hodnoty.|  
|[Idiasymbol::get_isaggregated –](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|`BOOL`|`TRUE`Pokud data je součástí typ agregovaná data (pouze v v8.0 DIA SDK a novější).|  
|[Idiasymbol::get_issplitted –](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|`BOOL`|`TRUE`Pokud jsou data rozdělena do agregaci více symbolů (pouze v v8.0 DIA SDK a novější).|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Délka bitfield; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol pro nadřazených kompilace, funkce nebo bloku.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Jakýkoli z typů povolených umístění; Podrobnosti najdete v tématu [umístění symbolu](../../debugger/debug-interface-access/symbol-locations.md)|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název proměnné.|  
|[Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Posun od obsah registrace; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_registerid –](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|`DWORD`|Zaregistrovat označení umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Relativní umístění dat v rámci jeho blok.|  
|[Idiasymbol::get_slot –](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|`DWORD`|Získá číslo pozice data.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagData` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_token –](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|Metadata token představující data.|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro typ proměnné.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu proměnné symbolu.|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud je v datech nezarovnané.|  
|[Idiasymbol::get_value –](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|Hodnota konstanty data.|  
|[Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Umístění dat v rámci spustitelný soubor.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud data je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [CV_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md)   
 [DataKind – výčet](../../debugger/debug-interface-access/datakind.md)   
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)