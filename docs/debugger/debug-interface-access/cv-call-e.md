---
title: Cv_call_e – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec5fea99994b891250dad85cfc43320848df98f9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602751"
---
# <a name="cvcalle"></a>CV_call_e
Určuje konvenci volání funkce.

> [!NOTE]
> Většina běžných hodnot výčtu jsou zdokumentované tady. V souboru hlaviček cvconst.h je k dispozici úplný výčet.

## <a name="syntax"></a>Syntaxe

```C++
typedef enum CV_call_e {
    CV_CALL_NEAR_C    = 0x00,
    CV_CALL_NEAR_FAST = 0x04,
    CV_CALL_NEAR_STD  = 0x07,
    CV_CALL_NEAR_SYS  = 0x09,
    CV_CALL_THISCALL  = 0x0b,
    CV_CALL_CLRCALL   = 0x16
} CV_call_e;
```

## <a name="elements"></a>Elementy
CV_CALL_NEAR_C určuje konvence volání funkce, pomocí operace push blízké zprava doleva. Volání funkce vymaže zásobníku.

Určuje CV_CALL_NEAR_FAST konvence volání funkce použitím téměř zleva doprava push se zaregistruje. Volaná funkce používá součtem bajtů parametrů k vymazání zásobníku.

CV_CALL_NEAR_STD určuje konvence volání funkce, pomocí téměř standardní volání (nabízených zprava doleva).

Určuje CV_CALL_NEAR_SYS konvence volání funkce, pomocí téměř systému volání.

Konvence volání funkce pomocí určuje CV_CALL_THISCALL `this` volání (`this` předán ukazatel v registru).

Určuje CV_CALL_CLRCALL volání funkce konvence podle CLR Common Language Runtime () (označované také jako spravovaný kód konvence volání).

## <a name="remarks"></a>Poznámky
Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiasymbol::get_callingconvention –](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
