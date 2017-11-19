---
title: "Výčet (přístup k rozhraní ladění SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerated types as symbols
- Enum symbol
ms.assetid: c777e2e6-88be-435b-b632-8d43f42b0b49
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b52a97fb549414c0f743c208f37530bc40c8a7c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="enum-debug-interface-access-sdk"></a>Výčet (Přístup k rozhraní ladění SDK)
Výčty jsou identifikovány `SymTagEnum` symboly. Každá hodnota výčtu se zobrazí jako podřízené třídy s `SymTagConstant` značky.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|`DWORD`|Jeden z [BasicType – výčet](../../debugger/debug-interface-access/basictype.md) hodnoty.|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Třída nadřazený tento výčet, pokud existuje.|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_constructor –](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`Pokud má výčet konstruktor.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud je označena jako const výčtu.|  
|[Idiasymbol::get_hasassignmentoperator –](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`Pokud má výčet operátor přiřazení.|  
|[Idiasymbol::get_hascastoperator –](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`Pokud má výčet operátor přetypování.|  
|[Idiasymbol::get_hasnestedtypes –](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`Pokud má výčet vnořené typy.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`DWORD`|Délka tento výčet v bajtech.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol uzavření [kompilace](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název výčtového typu.|  
|[Idiasymbol::get_nested –](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`Pokud je vnořený výčtu.|  
|[Idiasymbol::get_overloadedoperator –](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`Pokud má výčet všechny přetížené operátory.|  
|[Idiasymbol::get_packed –](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`Pokud se nachází v balení výčtu.|  
|[Idiasymbol::get_scoped –](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`Pokud v neglobální lexikální oboru se zobrazuje ve výčtu.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagEnum` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro základní typ.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu.|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud je výčet nezarovnané.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud výčtu je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)