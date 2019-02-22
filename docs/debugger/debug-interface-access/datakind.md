---
title: Datakind – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 21630bea3022769d18748190c2a2d24c0e519a3c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608488"
---
# <a name="datakind"></a>DataKind
Určuje konkrétní obor datové hodnoty.

## <a name="syntax"></a>Syntaxe

```C++
enum DataKind {
    DataIsUnknown,
    DataIsLocal,
    DataIsStaticLocal,
    DataIsParam,
    DataIsObjectPtr,
    DataIsFileStatic,
    DataIsGlobal,
    DataIsMember,
    DataIsStaticMember,
    DataIsConstant
};
```

## <a name="elements"></a>Elementy
Nelze určit DataIsUnknown datový symbol.

Položka DataIsLocal dat je místní proměnné.

Položka DataIsStaticLocal dat je statické místní proměnné.

Položka DataIsParam dat je formální parametr.

Položka DataIsObjectPtr dat je ukazatelem na objekt (`this`).

Položka DataIsFileStatic dat je proměnnou s rozsahem souboru.

Položka DataIsGlobal dat je globální proměnné.

Položka DataIsMember dat je proměnná člena objektu.

Položka DataIsStaticMember dat je statická proměnná třídy.

Položka DataIsConstant dat je konstantní hodnota.

## <a name="remarks"></a>Poznámky
Jsou vrácené hodnoty v tento výčet [idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)
