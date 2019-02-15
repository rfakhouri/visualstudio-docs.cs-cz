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
ms.openlocfilehash: bf8e59bf79355b4e610091ac8662b8d2a01af322
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318677"
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
DataIsUnknown  
Datový symbol nejde určit.

DataIsLocal  
Položka dat je místní proměnné.

DataIsStaticLocal  
Položka dat je statické místní proměnné.

DataIsParam  
Položka dat je formální parametr.

DataIsObjectPtr  
Položka dat je ukazatelem na objekt (`this`).

DataIsFileStatic  
Položka dat je proměnnou s rozsahem souboru.

DataIsGlobal  
Položka dat je globální proměnné.

DataIsMember  
Položka dat je proměnná člena objektu.

DataIsStaticMember  
Položka dat je statická proměnná třídy.

DataIsConstant  
Položka dat je konstantní hodnota.

## <a name="remarks"></a>Poznámky
Jsou vrácené hodnoty v tento výčet [idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
[Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)
