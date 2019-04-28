---
title: VTable | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- VTable symbol
- virtual tables
ms.assetid: c8be6692-7d2a-4721-99d3-8e2e565bb8a1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1f630c744a799183fe790e8b3067d0fc13378bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62853310"
---
# <a name="vtable"></a>VTable
Virtuální tabulky je identifikován `SymTagVTable` symbol.

## <a name="properties"></a>Vlastnosti
 V následující tabulce jsou uvedeny další platné vlastnosti pro tento typ symbolu.

|Vlastnost|Datový typ|Popis|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbol, který vlastní tuto tabulku VTable třídy.|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE` Pokud třída tabulku VTable je označená jako konstanta.|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol ohraničující kompilace.|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagVTable` (jeden z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol tabulce VTable [vtableshape –](../../debugger/debug-interface-access/vtableshape.md).|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbol.|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE` Pokud je třída tabulku VTable nezarovnaných.|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE` Pokud třída tabulku VTable je označená jako volatile.|

## <a name="see-also"></a>Viz také
- [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)
- [VTableShape](../../debugger/debug-interface-access/vtableshape.md)