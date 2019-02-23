---
title: IDebugCoreServer2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2
helpviewer_keywords:
- IDebugCoreServer2 interface
ms.assetid: 9c47d0a6-9eb1-464e-bd44-fa2b552d4d36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f4f01bb8e86e733bef3940a4772f52b28080628
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712382"
---
# <a name="idebugcoreserver2"></a>IDebugCoreServer2
Toto rozhraní se používá k reprezentaci a získávání informací ze serveru na počítači v síti.

## <a name="syntax"></a>Syntaxe

```
IDebugCoreServer2 : IUknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Visual Studio implementuje toto rozhraní, která bude představovat server. Každou instanci sady Visual Studio vytvoří instanci tohoto rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Poskytovatel port. Tento vlastní port obdrží toto rozhraní ve volání [události](../../../extensibility/debugger/reference/idebugportevents2-event.md).

 Ladicí stroj můžete získat toto rozhraní nepřímo prostřednictvím volání [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) (která vrací [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md), rozhraní, která je odvozena z `IDebugCoreServer2`).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugCoreServer2`.

|Metoda|Popis|
|------------|-----------------|
|[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)|Získá název a atributy počítače.|
|[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)|Získá název počítače.|
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)|Získá dodavatele portu, která existuje na počítači.|
|[GetPort](../../../extensibility/debugger/reference/idebugcoreserver2-getport.md)|Získá port, který již existuje v počítači.|
|[EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)|Vytvoří čítač pro všechny porty na počítači.|
|[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)|Vytvoří čítač pro všechny dodavatele portu na počítači.|
|[GetMachineUtilities_V7](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7.md)|Získá nástroje počítač pro počítač.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní se také používá sada Visual Studio procházet procesy běžící na počítačích v síti.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)