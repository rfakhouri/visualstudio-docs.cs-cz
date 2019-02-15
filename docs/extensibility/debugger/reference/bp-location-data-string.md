---
title: BP_LOCATION_DATA_STRING | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 44fbd40528196fdebee852d89108cf6205e5db71
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318187"
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
Používá k nastavení datové zarážky, které jsou založeny na řetězec, který může uživatel zadat z integrovaného vývojového prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _BP_LOCATION_DATA_STRING {
    IDebugThread2* pThread;
    BSTR           bstrContext;
    BSTR           bstrDataExpr;
    DWORD          dwNumElements;
} BP_LOCATION_DATA_STRING;
```

## <a name="members"></a>Členové
`pThread`  
[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákno, na kterém dochází k zarážce.

`bstrContext`  
Kontext zarážky v kódu, obvykle název metody nebo funkce jako zobrazení zásobníku volání.

`bstrDataExpr`  
Řetězec dat, které uživatel zadá nastavit zarážku.

`dwNumElements`  
Počet prvků v řetězci data, ve kterém dochází k zarážce.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktury v rámci sjednocení.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
