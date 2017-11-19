---
title: UDT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SymTagUDT symbol
- user-defined type (UDT) symbol
- unions, as symbols
- UDT symbol
- structs [C++]
ms.assetid: f12459dd-c64d-4cc9-9ee3-a56e19e9e573
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 975e739a3cb6ab4424875845b56b04643def107d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="udt"></a>UDT
Každý třída, struktura a sjednocení je identifikována `SymTagUDT` symbol. Každý člen, funkce, data, nebo vnořené typy a každý základní třídy, se zobrazí jako podřízenou třída uživatelem definovaný typ (UDT).  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbol pro nadřazené třídy, pokud existuje.|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_constructor –](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`Pokud UDT má konstruktor.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud UDT je označena jako konstanta.|  
|[Idiasymbol::get_hasassignmentoperator –](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`Pokud UDT má všechny operátory přiřazení definované.|  
|[Idiasymbol::get_hascastoperator –](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`Pokud UDT má všechny operátory přetypování definované.|  
|[Idiasymbol::get_hasnestedtypes –](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`Pokud UDT má definice vnořené typy.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`LONGLONG`|Velikost v bajtech UDT.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol uzavření [kompilace](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název UDT.|  
|[Idiasymbol::get_nested –](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`Pokud UDT je vnořený.|  
|[Idiasymbol::get_overloadedoperator –](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`Pokud přetížené operátory jsou definovány pro UDT.|  
|[Idiasymbol::get_packed –](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`Pokud UDT je zabalena.|  
|[Idiasymbol::get_scoped –](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`Pokud se zobrazí UDT v neglobální lexikální oboru.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagUDT` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|Určuje, zda je tato struktura, třídu nebo sjednocení; Podrobnosti najdete v tématu [UdtKind – výčet](../../debugger/debug-interface-access/udtkind.md).|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud UDT nezarovnané.|  
|[Idiasymbol::get_virtualtableshape –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|Typ na virtuální tabulku.|  
|[Idiasymbol::get_virtualtableshapeid –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|ID virtuální tabulku tvar symbolu.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud UDT je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)