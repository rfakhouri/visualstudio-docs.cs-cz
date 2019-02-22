---
title: IDebugModuleLoadEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModuleLoadEvent2
helpviewer_keywords:
- IDebugModuleLoadEvent2 interface
ms.assetid: 7d26fb23-5d49-4ba7-b7c5-3aed4d7be81e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 689fd873bc753e885f0e1efad177a26d524bb030
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687325"
---
# <a name="idebugmoduleloadevent2"></a>IDebugModuleLoadEvent2
Toto rozhraní je odeslaný ladicího stroje (DE) pro správce ladění relace (SDM) při modul je načten nebo byla uvolněna.

## <a name="syntax"></a>Syntaxe

```
IDebugModuleLoadEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní k sestavě, že modul byl načten nebo byla uvolněna. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt událostí do sestavy modul byl načten nebo byla uvolněna. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který je poskytnut pomocí SDM, když je připojen k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody `IDebugModuleLoadEvent2`.

|Metoda|Popis|
|------------|-----------------|
|[GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)|Získá modul, který je načten nebo byla uvolněna.|

## <a name="remarks"></a>Poznámky
 Visual Studio používá tuto událost zachovat **moduly** aktuální okno.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)