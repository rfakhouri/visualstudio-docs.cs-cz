---
title: IEnumDebugReferenceInfo2::Next | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2::Next
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Next
ms.assetid: 70b31a57-1701-4757-9e7e-63ec60a71b3c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a49e5c250b1df196ad2a2607c1518ed7411cbe3e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865989"
---
# <a name="ienumdebugreferenceinfo2next"></a>IEnumDebugReferenceInfo2::Next
Vrátí další sadu elementů z výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Next(
   ULONG                   celt,
   DEBUG_REFERENCE_INFO ** rgelt,
   ULONG*                  pceltFetched
);
```

```csharp
int Next(
   uint                   celt,
   DEBUG_REFERENCE_INFO[] rgelt,
   ref uint               pceltFetched
);
```

#### <a name="parameters"></a>Parametry
 `celt`

 [in] Počet prvků, které mají načíst. Také určuje maximální velikost `rgelt` pole.

 `rgelt`

 [out v] Pole [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) prvků, které mají být vyplněna.

 `pceltFetched`

 [out] Vrátí počet prvků ve skutečnosti vrácených v `rgelt`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` pokud menší než požadovaný počet prvků, které může být vrácena; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)