---
title: BP_LOCATION_CODE_FUNC_OFFSET | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_FUNC_OFFSET
helpviewer_keywords:
- BP_LOCATION_CODE_FUNC_OFFSET structure
ms.assetid: ab38f7ca-fa01-4cf3-a06c-56cbb7207617
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 90f624bf012354dbd438f0fff079e13da756f079
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318026"
---
# <a name="bplocationcodefuncoffset"></a>BP_LOCATION_CODE_FUNC_OFFSET
Popisuje umístění posunu zarážky ve funkci v kódu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _BP_LOCATION_CODE_FUNC_OFFSET {
    BSTR                     bstrContext;
    IDebugFunctionPosition2* pFuncPos;
} BP_LOCATION_CODE_FUNC_OFFSET;
```

## <a name="members"></a>Členové
`bstrContext`  
Kontext k zarážce, obvykle název metody nebo funkce jako zobrazené v zásobníku volání.

`pFuncPos`  
[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md) objekt, který popisuje název funkce a relativní pozice začátku funkce.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktury v rámci sjednocení.

`pFuncPos` Člen označuje, kde nastavit zarážku funkce.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)
