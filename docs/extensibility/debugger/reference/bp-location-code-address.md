---
title: BP_LOCATION_CODE_ADDRESS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_LOCATION_CODE_ADDRESS
helpviewer_keywords:
- BP_LOCATION_CODE_ADDRESS structure
ms.assetid: 83c9da8b-19d9-4be5-b225-854543654901
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
ms.openlocfilehash: 51137b5a5a69c80ecd7129d4c645f63b5805d27d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66319134"
---
# <a name="bplocationcodeaddress"></a>BP_LOCATION_CODE_ADDRESS
Popisuje umístění zarážky na adrese v kódu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _BP_LOCATION_CODE_ADDRESS {
    BSTR bstrContext;
    BSTR bstrModuleUrl;
    BSTR bstrFunction;
    BSTR bstrAddress;
} BP_LOCATION_CODE_ADDRESS;
```

## <a name="members"></a>Členové
`bstrContext`\
Kontext k zarážce, obvykle název metody nebo funkce jako zobrazené v zásobníku volání.

`bstrModuleUrl`\
Adresa URL modulu, který obsahuje zarážku.

`bstrFunction`\
Název funkce, která obsahuje zarážku.

`bstrAddress`\
Adresa zarážky, které je analyzován podle vyhodnocovače výrazů pro vytvoření vazby na [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktury v rámci sjednocení.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
