---
title: Udtkind – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 511beae100529f0db555eca0a8ddb995d7a335d1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636577"
---
# <a name="udtkind"></a>UdtKind
Popisuje různé uživatelem definovaný typ (UDT).

## <a name="syntax"></a>Syntaxe

```C++
enum UdtKind {
    UdtStruct,
    UdtClass,
    UdtUnion,
    UdtInterface
};
```

## <a name="elements"></a>Elementy
UdtStruct UDT je struktura.

UdtClass UDT je třída.

UdtUnion UDT je sjednocení.

UdtInterface UDT je rozhraní.

## <a name="remarks"></a>Poznámky
Jsou vrácené hodnoty v tento výčet [idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)
