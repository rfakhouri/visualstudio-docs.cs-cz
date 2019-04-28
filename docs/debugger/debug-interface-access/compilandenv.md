---
title: Compilandenv – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CompilandEnv symbol
ms.assetid: 808404bb-ece1-47f1-b9ea-c76d4d86ddd9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b935c9c79fd618c96f44b2660c274f657f81014e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62555205"
---
# <a name="compilandenv"></a>CompilandEnv
Kompilátor může obsahovat další proměnné prostředí se symboly. Existuje jedna `SymTagCompilandEnv` symbolů pro každou z těchto proměnných.

## <a name="properties"></a>Vlastnosti
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.

|Vlastnost|Datový typ|Popis|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol kompilace nadřazené.|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název proměnné.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagCompilandEnv` (jeden z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|
|[IDiaSymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|Obsah řetězce s hodnotou proměnné (`VT_BSTR`).|

## <a name="see-also"></a>Viz také
- [Kompilant](../../debugger/debug-interface-access/compiland.md)
- [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)