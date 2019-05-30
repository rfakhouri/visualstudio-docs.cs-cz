---
title: IDebugPendingBreakpoint2::GetBreakpointRequest | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::GetBreakpointRequest
helpviewer_keywords:
- IDebugPendingBreakpoint2::GetBreakpointRequest method
- GetBreakpointRequest method
ms.assetid: cb1e36aa-4302-455c-98fb-6638a1ef5c46
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 37bc4fb6421aa0c04afcf91d690e354e368c4055
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347828"
---
# <a name="idebugpendingbreakpoint2getbreakpointrequest"></a>IDebugPendingBreakpoint2::GetBreakpointRequest
Získá požadavek zarážku, která byla použita k vytvoření této čekající zarážka.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetBreakpointRequest( 
   IDebugBreakpointRequest2** ppBPRequest
);
```

```csharp
int GetBreakpointRequest( 
   out IDebugBreakpointRequest2 ppBPRequest
);
```

## <a name="parameters"></a>Parametry
`ppBPRequest`\
[out] Vrátí [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) objekt představující zarážku požadavek, který byl použit k vytvoření tohoto čekajících zarážek.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud zarážka byla odstraněna.

## <a name="see-also"></a>Viz také:
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)