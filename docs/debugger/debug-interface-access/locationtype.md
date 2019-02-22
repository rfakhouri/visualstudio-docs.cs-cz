---
title: Locationtype – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: faff61833cb130902efbd64d60a16f74c507a3e2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56627932"
---
# <a name="locationtype"></a>LocationType
Označuje druh informace o poloze, které jsou obsaženy v symbolu.

## <a name="syntax"></a>Syntaxe

```C++
enum LocationType {
    LocIsNull,
    LocIsStatic,
    LocIsTLS,
    LocIsRegRel,
    LocIsThisRel,
    LocIsEnregistered,
    LocIsBitField,
    LocIsSlot,
    LocIsIlRel,
    LocInMetaData,
    LocIsConstant,
    LocTypeMax
};
```

## <a name="elements"></a>Elementy
`LocIsNull` Informace o umístění není k dispozici.

`LocIsStatic` Umístění je statická.

`LocIsTLS` Umístění je v místním úložišti vláken.

`LocIsRegRel` Umístění je relativní k registru.

`LocIsThisRel` Umístění je `this`– relativní.

`LocIsEnregistered` Umístění je v registru.

`LocIsBitField` Umístění je ve bitového pole.

`LocIsSlot` Umístění je slot Microsoft Intermediate Language (MSIL).

`LocIsIlRel` Umístění je relativní vůči jazyka MSIL.

`LocInMetaData` Umístění je v metadatech.

`LocIsConstant` Umístění je konstantní hodnotu.

`LocTypeMax` Počet typů umístění tohoto výčtu.

## <a name="remarks"></a>Poznámky
Vlastnosti, které jsou k dispozici [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) rozhraní závisí na umístění symbolu v souboru bitové kopie. Další informace najdete v tématu [umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md).

Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)
- [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)
