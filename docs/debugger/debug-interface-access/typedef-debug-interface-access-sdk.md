---
title: "TypeDef (přístup k rozhraní ladění SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Typedef symbol [DIA SDK]
ms.assetid: 9ab441b9-cc72-47fa-83e2-87b3c2b891b4
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e7f1b3d7bcc7203755383201d24269e579919e5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="typedef-debug-interface-access-sdk"></a>Typedef (Přístup k rozhraní ladění SDK)
Symboly s `SymTagTypedef` značky zavést názvy pro ostatní typy.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|`DWORD`|Jeden z [BasicType – výčet](../../debugger/debug-interface-access/basictype.md) hodnoty.|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Nadřazená třída typedef, pokud existuje.|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_constructor –](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`Pokud tato typedef má konstruktor.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud tato definice typu je označena jako konstanta.|  
|[Idiasymbol::get_hasassignmentoperator –](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`Pokud tato typedef má operátor přiřazení.|  
|[Idiasymbol::get_hascastoperator –](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`Pokud tato typedef má operátor přetypování.|  
|[Idiasymbol::get_hasnestedtypes –](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`Pokud tato typedef má vnořené typy.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Délka této typedef v bajtech.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol nadřazených kompilace.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název typedef.|  
|[Idiasymbol::get_nested –](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`Pokud tato typedef vnořen v lexikální oboru.|  
|[Idiasymbol::get_overloadedoperator –](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`Pokud tato typedef má přetížené operátor.|  
|[Idiasymbol::get_packed –](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`Pokud tato definice typu je zabalena.|  
|[Idiasymbol::get_reference –](../../debugger/debug-interface-access/idiasymbol-get-reference.md)|`BOOL`|`TRUE`Pokud je tato definice typu odkaz.|  
|[Idiasymbol::get_scoped –](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`Pokud je tato definice typu v neglobální lexikální oboru.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagTypedef` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro základní typ.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu.|  
|[Idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|Jeden z [UdtKind – výčet](../../debugger/debug-interface-access/udtkind.md) hodnoty.|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud tato typedef není zarovnána.|  
|[Idiasymbol::get_virtualtableshape –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|Symbol, který popisuje tvaru virtuální tabulku.|  
|[Idiasymbol::get_virtualtableshapeid –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|ID virtuální tabulku tvar symbolu.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud tato definice typu je označena jako volatile.|  
  
## <a name="remarks"></a>Poznámky  
 Vzhledem k tomu, že definice typu může představovat třídu, ukazatel nebo uživatelem definovaný typ (UDT), symbol pro definici typu sdílí stejné vlastnosti jako jeden z těchto dalších typů symbolů.  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)