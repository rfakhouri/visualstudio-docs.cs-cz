---
title: IDebugReturnValueEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReturnValueEvent2
helpviewer_keywords:
- IDebugReturnValueEvent2
ms.assetid: 2daded43-e427-4fbb-a19e-f3834e3723af
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 03f3a46c7213a48b527f2756e5a4915ca59e48f8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345658"
---
# <a name="idebugreturnvalueevent2"></a>IDebugReturnValueEvent2
Toto rozhraní je odesílat pomocí ladicího stroje (DE) Správce ladění relace (SDM) po přechodu z celkového počtu nebo funkci.

## <a name="syntax"></a>Syntaxe

```
IDebugReturnValueEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní k hlášení návratová hodnota z funkce, která má byla zvyšována z nebo v průběhu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt událostí k hlášení návratovou hodnotu funkce. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který je poskytnut pomocí SDM, když je připojen k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody `IDebugReturnValueEvent2`.

|Metoda|Popis|
|------------|-----------------|
|[GetReturnValue](../../../extensibility/debugger/reference/idebugreturnvalueevent2-getreturnvalue.md)|Získá hodnotu vrácenou v krokování ve funkci.|

## <a name="remarks"></a>Poznámky
 Hodnota vrácená funkcí lze získat voláním [GetReturnValue](../../../extensibility/debugger/reference/idebugreturnvalueevent2-getreturnvalue.md). Vrácená hodnota se zobrazí v **automatické hodnoty** okna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)