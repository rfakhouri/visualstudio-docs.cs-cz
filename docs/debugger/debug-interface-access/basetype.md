---
title: "Základní typ BaseType | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: BaseType symbol [DIA SDK]
ms.assetid: 2f9e22e6-8360-496a-ac6b-17a5a56b0c46
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76e4b2ce7500263d803816c759b97ba11bab83aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="basetype"></a>BaseType
Základní typy jsou určeny `SymTagBaseType` symboly.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|`DWORD`|Jedna z hodnot [BasicType – výčet](../../debugger/debug-interface-access/basictype.md).|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud základní typ je označena jako const.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`LONGLONG`|Velikost v bajtech, základního typu.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol uzavření [kompilace](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagBaseType` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud je základní typ nezarovnané.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud základní typ je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [BasicType – výčet](../../debugger/debug-interface-access/basictype.md)   
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)