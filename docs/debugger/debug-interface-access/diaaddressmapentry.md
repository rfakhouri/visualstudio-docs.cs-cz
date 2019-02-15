---
title: Diaaddressmapentry – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b472c52934353e6324d72077f8ea878467159cbd
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318638"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
Popisuje položky v mapování adres.

## <a name="syntax"></a>Syntaxe

```C++
struct DiaAddressMapEntry {
    DWORD rva,
    DWORD rvaTo
};
```

## <a name="elements"></a>Elementy
`rva`  
Relativní virtuální adresu (RVA) v bitové kopii A.

`rvaTo`  
Relativní virtuální adresu `rva` je namapována na obrázku B.

## <a name="remarks"></a>Poznámky
Mapování adresy zajišťuje překlad z jedné image rozložení (A) do jiného (B). Pole `DiaAddressMapEntry` struktury seřazené podle `rva` definuje mapu adresu.

Přeložit adresy, `addrA`, obrázku A na adresu, `addrB`, obrázku B, proveďte následující kroky:

1. Hledat na mapě položce, `e`, s největší `rva` menší než nebo rovno `addrA`.

2. Nastavte `delta = addrA - e.rva`.

3. Nastavte `addrB = e.rvaTo + delta`.

    Pole `DiaAddressMapEntry` struktury je předán [idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: dia2.h

## <a name="see-also"></a>Viz také
[Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
