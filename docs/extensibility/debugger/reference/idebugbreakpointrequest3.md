---
title: IDebugBreakpointRequest3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest3
helpviewer_keywords:
- IDebugBreakpointRequest3
ms.assetid: 8a042beb-b319-48e3-b3c8-9c8336ab371b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c45b1bae11710063d089aeca61a9d20fb6e907a4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691095"
---
# <a name="idebugbreakpointrequest3"></a>IDebugBreakpointRequest3
Toto rozhraní představuje informace potřebné k vytvoření a připojení jakýkoli typ zarážky. Je rozšířením [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md).

## <a name="syntax"></a>Syntaxe

```
IDebugBreakpointRequest3 : IDebugBreakpointRequest2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Správce ladění relace (SDM) obvykle implementuje toto rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Ladicí stroj (DE) toto rozhraní má přístup k voláním [QueryInterface](/cpp/atl/queryinterface) na rozhraní IDebugBreakpointRequest2 obdrželi volání [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod zděděných z [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md), `IDebugBreakpointRequest3` rozhraní poskytuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)|Získá informace o požadavku zarážky, popisující tuto zarážku žádost.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní se používá na další informace na DE prostřednictvím [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury. Tyto další informace obsahuje ID dodavatele je DE (ve formě identifikátoru GUID), název zarážku s trasováním a název omezení zarážku.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)