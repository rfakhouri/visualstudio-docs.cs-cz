---
title: "Functionargtype – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: FunctionArgType symbol
ms.assetid: 9f072fd3-0b99-405c-af99-fd44cd56fd73
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e9421481a90ad45e6ddca0623483e681d0c90422
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="functionargtype"></a>FunctionArgType
Každý parametr funkce je identifikovaná `SymTagFunctionArgType` symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platný vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Pro nadřazený prvek functiontype – symbol|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol uzavření [kompilace](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagFunctionArgType` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Typ parametru.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbolu.|  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Functiontype –](../../debugger/debug-interface-access/functiontype.md)