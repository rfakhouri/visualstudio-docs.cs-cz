---
title: "Poznámky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SymTabAnnotation symbol
- Annotation symbol
ms.assetid: eb9f759b-98a5-45fc-b085-91f1f2666e72
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 330b675f0bf6f9b656b6bb9742560e8da09477d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="annotation"></a>Poznámka
Kód programu umístění může být opatřena poznámkou `SymTagAnnotation` symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Posunutí součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Část součástí umístění; Podrobnosti najdete v tématu [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|Jeden z [DataKind – výčet](../../debugger/debug-interface-access/datakind.md) hodnoty.|  
|[Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Relativní umístění tato anotace v rámci jeho modul.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagAnnotation` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[Idiasymbol::get_value –](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|Hodnota konstanty data.|  
|[Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Umístění této poznámky v rámci spustitelné bitové kopie.|  
  
## <a name="see-also"></a>Viz také  
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)