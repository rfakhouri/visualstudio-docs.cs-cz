---
title: IEnumDebugErrorBreakpoints2::Next | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::Next
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::Next
ms.assetid: 6a3dee11-5267-4d77-9e28-6a38413ba70b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bdd1993d901d7fc22b6bf20efdec537cc22025e2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62867310"
---
# <a name="ienumdebugerrorbreakpoints2next"></a>IEnumDebugErrorBreakpoints2::Next
Vrátí další sadu elementů z výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Next(
   ULONG                    celt,
   IDebugErrorBreakpoint2** rgelt,
   ULONG*                   pceltFetched
);
```

```csharp
int Next(
   uint                     celt,
   IDebugErrorBreakpoint2[] rgelt,
   ref uint                 pceltFetched
);
```

#### <a name="parameters"></a>Parametry
 `celt`

 [in] Počet prvků, které mají načíst. Také určuje maximální velikost `rgelt` pole.

 `rgelt`

 [out v] Pole [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) prvků, které mají být vyplněna.

 `pceltFetched`

 [out] Vrátí počet prvků ve skutečnosti vrácených v `rgelt`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` pokud menší než požadovaný počet prvků, které může být vrácena; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
- [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)