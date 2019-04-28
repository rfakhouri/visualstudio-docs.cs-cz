---
title: IDebugPendingBreakpoint2::Bind | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::Bind
helpviewer_keywords:
- Bind method
- IDebugPendingBreakpoint2::Bind method
ms.assetid: 46e3f307-219d-40cd-a929-d41399c60ecf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 56a437902d7992c0c29df01d590b1a70afe10536
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842675"
---
# <a name="idebugpendingbreakpoint2bind"></a>IDebugPendingBreakpoint2::Bind
Vytvoří vazbu zarážka čeká na jeden nebo více umístění kódu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Bind( 
   void 
);
```

```csharp
int Bind();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud zarážka byla odstraněna.

## <a name="remarks"></a>Poznámky
 Když tato metoda je volána, ladicí stroj (DE) by měl pokusit o svázání tohoto čekající zarážka ke všem místům kódu, které odpovídají.

 Po návratu tato metoda volající potřebuje čekání na události, které naznačují, že čekající zarážka má vázané nebo před za předpokladu, že došlo k chybě a, které volá, aby [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md) nebo [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md).methods projde všechny zarážky s vazbou nebo došlo k chybě, v uvedeném pořadí.

## <a name="see-also"></a>Viz také
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)
- [IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
- [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)