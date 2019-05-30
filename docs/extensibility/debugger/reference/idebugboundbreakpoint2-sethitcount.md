---
title: IDebugBoundBreakpoint2::SetHitCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b8e59fadb019124cca111f23e99220b77df2a88d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66314477"
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
Nastaví počet průchodů pro vázaná zarážka.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetHitCount( 
   DWORD dwHitCount
);
```

```csharp
int SetHitCount( 
   uint dwHitCount
);
```

## <a name="parameters"></a>Parametry
`dwHitCount`\
[in] Počet přístupů k nastavení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud státu objekt vázaná zarážka nastavená na `BPS_DELETED` (součástí [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) výčet).

## <a name="remarks"></a>Poznámky
 Počet přístupů je počet průchodů této zarážky se aktivuje při spuštění aktuální relace.

 Tato metoda je obvykle volána ladicí stroj aktualizovat aktuální počet přístupů na této zarážce.

## <a name="see-also"></a>Viz také:
- [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)
- [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)