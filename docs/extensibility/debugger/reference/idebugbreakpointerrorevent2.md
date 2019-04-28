---
title: IDebugBreakpointErrorEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointErrorEvent2
helpviewer_keywords:
- IDebugBreakpointErrorEvent2
ms.assetid: adee79df-8db5-4510-a7df-c50f4dbf5e35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5188f64d9eec837bf8f2fc630f7c74a7924d792
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877154"
---
# <a name="idebugbreakpointerrorevent2"></a>IDebugBreakpointErrorEvent2
Toto rozhraní informuje správce ladění relace (SDM), čekající zarážkou nebylo možné svázat načíst programu, buď z důvodu upozornění nebo chybu.

## <a name="syntax"></a>Syntaxe

```
IDebugBreakpointErrorEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní jako součást jeho podporu pro zarážky. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) musí implementovat rozhraní na stejný objekt jako toto rozhraní (SDM používá [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní).

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt událost, když čekající zarážka nemůže být vázán k laděnému programu. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytnutých SDM při připojení k laděnému programu funkce zpětného volání.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugBreakpointErrorEvent2`.

|Metoda|Popis|
|------------|-----------------|
|[GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)|Získá [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) rozhraní, které popisuje upozornění nebo chyby.|

## <a name="remarks"></a>Poznámky
 Pokaždé, když je vázán na zarážku, událost je odeslána SDM. Pokud nemůže být vázán zarážku, `IDebugBreakpointErrorEvent2` odeslané; jinak [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) se odesílají.

 Například pokud podmínka přidružená k čekající zarážka nepodaří analyzovat nebo vyhodnocení, upozornění přijde, že v tuto chvíli nemůže být vázaný čekající zarážka. To může dojít, pokud ještě nenačetl kód pro zarážku.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)