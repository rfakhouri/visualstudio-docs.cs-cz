---
title: "Lexikální hierarchie typů symbolů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: symbols [DIA SDK], type hierarchies
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0077ababbbcfb1b2dff77a8847f5e0e0671241be
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="lexical-hierarchy-of-symbol-types"></a>Lexikální hierarchie typů symbolů
Následující tabulka uvádí typy symbol v lexikální hierarchie.  
  
## <a name="symbol-types"></a>Symbol typy  
  
|Typ symbolu|Popis|  
|-----------------|-----------------|  
|[Poznámky](../../debugger/debug-interface-access/annotation.md)|Určuje umístění s poznámkami v programovém kódu.|  
|[Blok](../../debugger/debug-interface-access/block.md)|Určuje vnořené obory ve funkcích.|  
|`Compiland`|Určuje `compiland` propojený soubor .exe.|  
|[Compilanddetails –](../../debugger/debug-interface-access/compilanddetails.md)|Určuje kompilace data, která může vyžadovat načítání podrobností o další kompilace a proto dojít běhu režie pro načtení.|  
|[Compilandenv –](../../debugger/debug-interface-access/compilandenv.md)|Určuje žádné další proměnné prostředí důležité pro kompilaci souboru pro kompilaci.|  
|[Vlastní (přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/custom-debug-interface-access-sdk.md)|Určuje symbol, uživatelem definované.|  
|[Data (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/data-debug-interface-access-sdk.md)|Určuje tyto proměnné jako parametry, místní proměnné, globální proměnné a členy třídy.|  
|[Soubor EXE](../../debugger/debug-interface-access/exe.md)|Určuje globální obor dat; odpovídá celý soubor .exe nebo .dll.|  
|[Funcdebugend –](../../debugger/debug-interface-access/funcdebugend.md)|Určuje funkce, která má bod definované v ladění, který je pro ukončení.|  
|[Funcdebugstart –](../../debugger/debug-interface-access/funcdebugstart.md)|Určuje funkce, která má bod definované v ladění, která má začít.|  
|[Funkce (přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/function-debug-interface-access-sdk.md)|Určuje funkci.|  
|[Popisek (přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/label-debug-interface-access-sdk.md)|Určuje umístění v programovém kódu.|  
|[Publicsymbol –](../../debugger/debug-interface-access/publicsymbol.md)|Určuje externí symbol, který se zobrazí při sestavování spustitelný program.|  
|[Převodu](../../debugger/debug-interface-access/thunk.md)|Určuje `thunk`.|  
|[Usingnamespace –](../../debugger/debug-interface-access/usingnamespace.md)|Určuje `namespace`identifikátor.|  
  
> [!NOTE]
>  Další symbol vlastnosti může být k dispozici v závislosti na typ symbolu. Tyto vlastnosti jsou uvedeny v tématech jednotlivých symbol.  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)   
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)