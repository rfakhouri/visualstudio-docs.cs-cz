---
title: Stackframetypeenum – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dab674576655df3b4a695d97fdfdb42df2ffa449
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227261"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
Určuje typ rámce zásobníku.

## <a name="syntax"></a>Syntaxe

```C++
enum StackFrameTypeEnum {
    FrameTypeFPO,
    FrameTypeTrap,
    FrameTypeTSS,
    FrameTypeStandard,
    FrameTypeFrameData,
    FrameTypeUnknown = -1
};
```

## <a name="elements"></a>Elementy
`FrameTypeFPO`  
Tento parametr vynechán, ukazatel na rámec Informace o FPO k dispozici.

`FrameTypeTrap`  
Rámec depeše jádra.

`FrameTypeTSS`  
Rámec depeše jádra.

`FrameTypeStandard`  
Standardní EBP rámce zásobníku.

`FrameTypeFrameData`  
Tento parametr vynechán, ukazatel na rámec Rámec informace o datech k dispozici.

`FrameTypeUnknown`  
Snímek, který nemá dostupné žádné ladicí informace.

## <a name="remarks"></a>Poznámky
Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiastackframe::get_type –](../../debugger/debug-interface-access/idiastackframe-get-type.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
[Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)
