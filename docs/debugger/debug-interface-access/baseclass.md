---
title: "Baseclass – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user-defined types, base classes
- BaseClass symbol
- base classes, user-defined types
ms.assetid: 9375ca35-cb91-45f5-8903-7344ee4528e8
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a19dee7c2b31df52a379f6ef2044a862baed7972
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="baseclass"></a>BaseClass
Každý základní třída pro symbol uživatelem definovaný typ (UDT) je identifikována podřízenou s `SymTagBaseClass` značky. [Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md) vlastnost obsahuje symbol pro základní UDT a všechny vlastnosti základní UDT jsou k dispozici jako součást této baseclass – symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_access –](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Modifikátor přístupu u této základní třídy. Jeden z [CV_access_e – výčet](../../debugger/debug-interface-access/cv-access-e.md) hodnoty.|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbol nadřazených třídy (pokud existuje).|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_constructor –](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`Pokud základní třída má konstruktor.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud je označena jako const základní třídy.|  
|[Idiasymbol::get_hasassignmentoperator –](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`Pokud základní třída má operátor přiřazení.|  
|[Idiasymbol::get_hascastoperator –](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`Pokud základní třída má operátor přetypování.|  
|[Idiasymbol::get_hasnestedtypes –](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`Pokud základní třída má vnořené typy.|  
|[Idiasymbol::get_indirectvirtualbaseclass –](../../debugger/debug-interface-access/idiasymbol-get-indirectvirtualbaseclass.md)|`BOOL`|`TRUE`Pokud je nepřímý základní třídy.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`DWORD`|Délka této základní třídy v bajtech.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol nadřazených kompilace.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název základní třídy.|  
|[Idiasymbol::get_nested –](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`Pokud je vnořený základní třídy.|  
|[Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Posun z určitých podřízených objektů, který představuje základní třídu v rámci struktury.|  
|[Idiasymbol::get_overloadedoperator –](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`Pokud základní třída má všechny přetížené operátory.|  
|[Idiasymbol::get_packed –](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`Pokud se nachází v balení základní třídy.|  
|[Idiasymbol::get_scoped –](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`Pokud v neglobální oboru se zobrazuje základní třídy.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagBaseClass` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro základní třídu [UDT](../../debugger/debug-interface-access/udt.md).|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu.|  
|[Idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|Hodnota z [UdtKind – výčet](../../debugger/debug-interface-access/udtkind.md).|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud je základní třída nezarovnané.|  
|[Idiasymbol::get_virtualbaseclass –](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseclass.md)|`BOOL`|`TRUE`Pokud je virtuální základní třídy.|  
|[Idiasymbol::get_virtualbasedispindex –](../../debugger/debug-interface-access/idiasymbol-get-virtualbasedispindex.md)|`DWORD`|Index do tabulky virtuální základní posunutí.|  
|[Idiasymbol::get_virtualbasepointeroffset –](../../debugger/debug-interface-access/idiasymbol-get-virtualbasepointeroffset.md)|`LONG`|Posun virtuální základní ukazatele.|  
|[Idiasymbol::get_virtualbasetabletype –](../../debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype.md)|`IDiaSymbol*`|Typ ukazatele virtuální základní tabulky.|  
|[Idiasymbol::get_virtualtableshape –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|Symbol popisující typ na virtuální tabulku pro tento základní třídu.|  
|[Idiasymbol::get_virtualtableshapeid –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|ID virtuální tabulku tvar symbolu.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud základní třídy je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [UDT](../../debugger/debug-interface-access/udt.md)