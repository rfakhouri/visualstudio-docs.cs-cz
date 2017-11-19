---
title: "Převodu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- thunk properties [DIA SDK]
- thunk symbol
ms.assetid: 01abb95f-d89a-465c-a4eb-8e8509598c95
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 514a0d7cea56158cbe15d59d2a809968b3c86979
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="thunk"></a>Převod
Každý `thunk` je identifikována `SymTagThunk` značky.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_access –](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Atribut – modifikátor přístupu jeden z [CV_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md) hodnoty (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Posunutí součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasegment::get_addresssection –](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|`DWORD`|Část součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Uzavření třída nadřazeným prvkem, pokud existují (pouze v rámci DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID nadřazených symbolu nadřazené třídy (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|Hodnota TRUE, pokud převodu je označena jako konstanta (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_intro –](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|Hodnota TRUE, pokud je jinou bitovou šířku Úvod do virtuální funkce (pouze v DIA SDK V8.0 nebo novější)|  
|[Idiasymbol::get_isstatic –](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|Hodnota TRUE, pokud převodu se považuje za statickou (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Počet bajtů kódu převodu.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol pro nadřazených kompilace, bloku nebo funkce.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Koncové body mají statické location; Podrobnosti najdete v tématu [umístění symbolu](../../debugger/debug-interface-access/symbol-locations.md) výčtu.|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název převodu.|  
|[Idiasymbol::get_pure –](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|TRUE, pokud převodu je čistě virtuální (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Relativní umístění tohoto převodu v rámci jeho modul.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagThunk` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_targetoffset –](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|`DWORD`|Posun součástí umístění cíle převodu.|  
|[Idiasymbol::get_targetrelativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|`DWORD`|Relativní virtuální adresy převodu cíl v jeho vnějšího bloku.|  
|[Idiasymbol::get_targetsection –](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|`DWORD`|Část oddílu převodu cíle.|  
|[Idiasymbol::get_targetvirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|`ULONGLONG`|Umístění cíle převodu ve spustitelné bitové kopie.|  
|[Idiasymbol::get_thunkordinal –](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|`DWORD`|Převodu typu, podle definice [THUNK_ORDINAL – výčet](../../debugger/debug-interface-access/thunk-ordinal.md).|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Typ tohoto převodu (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud jinou bitovou šířku není zarovnána (pouze v DIA SDK V8.0 nebo novější),|  
|[Idiasymbol::get_virtual –](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE`Pokud jinou bitovou šířku virtuální (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Umístění tohoto převodu v rámci spustitelné bitové kopie.|  
|[Idiasymbol::get_virtualbaseoffset –](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|Posun v na virtuální tabulku pro tento převodu (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud jinou bitovou šířku je označena jako volatile (pouze v DIA SDK V8.0 nebo novější).|  
  
## <a name="see-also"></a>Viz také  
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [THUNK_ORDINAL – výčet](../../debugger/debug-interface-access/thunk-ordinal.md)