---
title: Lexikální hierarchie typů symbolů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], type hierarchies
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: dac4ae8357d62813abb3f4735ec6e1f8b552d324
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797483"
---
# <a name="lexical-hierarchy-of-symbol-types"></a>Lexikální hierarchie typů symbolů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující tabulka uvádí v lexikální hierarchie typů symbolů.  
  
## <a name="symbol-types"></a>Typů symbolů  
  
|Typ symbolu|Popis|  
|-----------------|-----------------|  
|[Poznámka](../../debugger/debug-interface-access/annotation.md)|Určuje umístění služby s poznámkami v kódu programu.|  
|[Blok](../../debugger/debug-interface-access/block.md)|Určuje vnořené obory ve funkcích.|  
|`Compiland`|Určuje `compiland` propojený soubor .exe.|  
|[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)|Určuje kompilantu data, která může vyžadovat načítání podrobností o další kompilace a proto se vám účtovat za běhu režie pro načtení.|  
|[CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)|Určuje libovolné proměnné prostředí důležité pro kompilaci souboru pro kompilaci.|  
|[Vlastní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/custom-debug-interface-access-sdk.md)|Určuje symbol definovaný uživatelem.|  
|[Data (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/data-debug-interface-access-sdk.md)|Určuje tyto proměnné jako parametry, místní proměnné, globální proměnné a členy třídy.|  
|[Exe](../../debugger/debug-interface-access/exe.md)|Určuje globální rozsah dat; odpovídá celý soubor .exe nebo .dll.|  
|[FuncDebugEnd](../../debugger/debug-interface-access/funcdebugend.md)|Určuje funkci, která obsahuje bod definovaný v ladění, které se do konce.|  
|[FuncDebugStart](../../debugger/debug-interface-access/funcdebugstart.md)|Určuje funkci, která obsahuje bod definovaný v ladění, která má začít.|  
|[Funkce (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/function-debug-interface-access-sdk.md)|Určuje funkci, která.|  
|[Popisek (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/label-debug-interface-access-sdk.md)|Určuje umístění v kódu programu.|  
|[PublicSymbol](../../debugger/debug-interface-access/publicsymbol.md)|Určuje externí symbol, který se zobrazí při vytváření spustitelného souboru.|  
|[Převod](../../debugger/debug-interface-access/thunk.md)|Určuje `thunk`.|  
|[UsingNameSpace](../../debugger/debug-interface-access/usingnamespace.md)|Určuje `namespace`identifikátor.|  
  
> [!NOTE]
>  Další symbol vlastnosti mohou být k dispozici v závislosti na typu symbol. Tyto vlastnosti jsou uvedeny v tématech pro jednotlivé symbol.  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)   
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)
