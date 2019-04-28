---
title: IEnumDebugBoundBreakpoints2::Next | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugBoundBreakpoints2::Next
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::Next
ms.assetid: cb3a249f-2282-4bdc-b6d8-a4ee4bfb8365
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 542acd97b39813633c1207d90217498dd6fa77b4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62867521"
---
# <a name="ienumdebugboundbreakpoints2next"></a>IEnumDebugBoundBreakpoints2::Next
Vrátí další sadu elementů z výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Next(
   ULONG                    celt,
   IDebugBoundBreakpoint2** rgelt,
   ULONG*                   pceltFetched
);
```

```csharp
int Next(
   uint                     celt,
   IDebugBoundBreakpoint2[] rgelt,
   ref uint                 pceltFetched
);
```

#### <a name="parameters"></a>Parametry
 `celt`

 [in] Počet prvků, které mají načíst. Také určuje maximální velikost `rgelt` pole.

 `rgelt`

 [out v] Pole [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) prvků, které mají být vyplněna.

 `pceltFetched`

 [out] Vrátí počet prvků ve skutečnosti vrácených v `rgelt`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` pokud menší než požadovaný počet prvků, které může být vrácena; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)
- [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)