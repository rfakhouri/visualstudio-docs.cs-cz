---
title: ArrayType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ArrayType symbol
ms.assetid: 1d973a3a-2bde-46df-8625-85d519bb3cc9
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49a11b76688efbee897a432e62020bb92996bb37
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="arraytype"></a>ArrayType
Pole je identifikována `SymTagArray` symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_arrayindextype –](../../debugger/debug-interface-access/idiasymbol-get-arrayindextype.md)|`IDiaSymbol*`|Symbol pro typ indexu pole.|  
|[Idiasymbol::get_arrayindextypeid –](../../debugger/debug-interface-access/idiasymbol-get-arrayindextypeid.md)|`DWORD`|ID typu symbolu index pole.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Pokud toto pole je označena jako const.|  
|[Idiasymbol::get_count –](../../debugger/debug-interface-access/idiasymbol-get-count.md)|`DWORD`|Počet položek v poli.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`LONGLONG`|Velikost v bajtech, toto pole.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol nadřazených kompilace.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_rank –](../../debugger/debug-interface-access/idiasymbol-get-rank.md)|`DWORD`|Pořadí FORTRAN multidimenzionálního pole.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagArray` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro typ pole elementu.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu pole elementu.|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Pokud je pole nezarovnané|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Pokud toto pole je označena jako volatile.|  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Dimenze](../../debugger/debug-interface-access/dimension.md)