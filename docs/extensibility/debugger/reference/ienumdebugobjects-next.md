---
title: IEnumDebugObjects::Next | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects::Next
helpviewer_keywords:
- IEnumDebugObjects::Next method
ms.assetid: e54c3055-6030-4dc9-9f7a-5e3ce75f252f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 33d9bf44d8d586c5e9206ff23ec69970b5a00449
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62866805"
---
# <a name="ienumdebugobjectsnext"></a>IEnumDebugObjects::Next
Tato metoda vrátí další sadu elementů z výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Next(
   ULONG          celt,
   IDebugObject** rgelt,
   ULONG*         pceltFetched
);
```

```csharp
int Next(
   uint           celt,
   IDebugObject[] rgelt,
   ref uint       pceltFetched
);
```

#### <a name="parameters"></a>Parametry
 `celt`

 [in] Počet prvků, které mají načíst. Také určuje maximální velikost `rgelt` pole.

 `rgelt`

 [out v] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) prvků, které mají být vyplněna.

 `pceltFetched`

 [out] Vrátí počet prvků ve skutečnosti vrácených v `rgelt`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` pokud menší než požadovaný počet prvků, které může být vrácena; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)