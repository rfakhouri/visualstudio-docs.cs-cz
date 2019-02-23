---
title: IDebugBreakpointRequest2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 01ac4013-96f9-4235-b289-f55f9e99558f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6a984634dbba0fc1d732fe98214a07d8d6c339d4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698102"
---
# <a name="idebugbreakpointrequest2"></a>IDebugBreakpointRequest2
Toto rozhraní představuje informace potřebné k vytvoření a připojení jakýkoli typ zarážky.

## <a name="syntax"></a>Syntaxe

```
IDebugBreakpointRequest2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Správce ladění relace (SDM) obvykle implementuje toto rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Ladicí stroj (DE) obdrží toto rozhraní přímo pomocí volání [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) Chcete-li vytvořit čekající zarážkou. Volání [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md) toto rozhraní můžete načíst z DE.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugBreakpointRequest2`.

|Metoda|Popis|
|------------|-----------------|
|[GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)|Získá typ umístění zarážky tohoto požadavku na zarážku.|
|[GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)|Získá informace o požadavku zarážky, popisující tuto zarážku žádost.|

## <a name="remarks"></a>Poznámky
 Po program laděn se načetl, volání [svázat](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) váže čekající zarážkou požadované umístění v programu.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)
- [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)
- [Bind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)