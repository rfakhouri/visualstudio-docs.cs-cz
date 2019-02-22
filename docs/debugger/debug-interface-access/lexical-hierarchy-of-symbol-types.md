---
title: Lexikální hierarchie typů symbolů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], type hierarchies
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a92f3f8f5174717b3fe3e992706a0f16478f99df
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56612800"
---
# <a name="lexical-hierarchy-of-symbol-types"></a>Lexikální hierarchie typů symbolů
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
- [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)
- [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
- [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)