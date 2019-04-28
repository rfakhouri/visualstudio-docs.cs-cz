---
title: Převodní rutina | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- thunk properties [DIA SDK]
- thunk symbol
ms.assetid: 01abb95f-d89a-465c-a4eb-8e8509598c95
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 872723e4aaf425b388ce8d05f9c8f9d631dd5ed9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62854382"
---
# <a name="thunk"></a>Převod
Každý `thunk` je identifikován `SymTagThunk` značky.

## <a name="properties"></a>Vlastnosti
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.

|Vlastnost|Datový typ|Popis|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Atribut modifikátor přístupu jeden z [cv_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md) hodnoty (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Posun součástí umístění. Podrobnosti najdete v tématu [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSegment::get_addressSection](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|`DWORD`|Část oddílu umístění. Podrobnosti najdete v tématu [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Vnější nadřazené třídu, pokud existují (jenom pod DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID nadřazené symbolu nadřazené třídy (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|TRUE, pokud jiné bitové šířce je označený jako konstanta (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|Hodnota TRUE, pokud jiné bitové šířce slouží jako úvod ke virtuální funkce (pouze v DIA SDK ve verzi 8.0 nebo novější)|
|[IDiaSymbol::get_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|TRUE, pokud převodní rutina se považuje za statické (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Počet bajtů kódu v jiné bitové šířce.|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol pro nadřazené kompilace, bloku nebo funkce.|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Koncové body mají statickou umístění. Podrobnosti najdete v tématu [umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md) výčtu.|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název jiné bitové šířce.|
|[IDiaSymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|TRUE, pokud jiné bitové šířce je čistě virtuální (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Relativní pozice tohoto převodní rutina v rámci jeho modulu.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagThunk` (jeden z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|
|[IDiaSymbol::get_targetOffset](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|`DWORD`|Posun součástí umístění cíle převodní rutina.|
|[IDiaSymbol::get_targetRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|`DWORD`|Relativní virtuální adresu cíle převodní rutina v jeho nadřazeném bloku.|
|[IDiaSymbol::get_targetSection](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|`DWORD`|Část část cíle.|
|[IDiaSymbol::get_targetVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|`ULONGLONG`|Pozici cíle převodní rutina v spustitelné bitové kopie.|
|[IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|`DWORD`|Převést typ, podle definice [thunk_ordinal – výčet](../../debugger/debug-interface-access/thunk-ordinal.md).|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Typ tohoto převodu (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE` Pokud převodní rutina není zarovnána (pouze v DIA SDK ve verzi 8.0 nebo novější)|
|[IDiaSymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE` Pokud převodní rutina je virtuální (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Pozice tohoto převodní rutina v rámci spustitelné bitové kopie.|
|[IDiaSymbol::get_virtualBaseOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|Posun v tabulce virtuální Tento převodní rutina (pouze v DIA SDK ve verzi 8.0 nebo novější).|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE` Pokud převodní rutina je označená jako volatile (pouze v DIA SDK ve verzi 8.0 nebo novější).|

## <a name="see-also"></a>Viz také
- [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
- [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)
- [THUNK_ORDINAL – výčet](../../debugger/debug-interface-access/thunk-ordinal.md)