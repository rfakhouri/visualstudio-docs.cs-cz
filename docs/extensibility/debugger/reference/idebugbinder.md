---
title: IDebugBinder | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder
helpviewer_keywords:
- IDebugBinder interface
ms.assetid: d1f31e5b-c6e2-4e02-8959-b3e86041b29c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bdcc5e9cc87bbe97a1ff9092e34c73b72274d775
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344346"
---
# <a name="idebugbinder"></a>IDebugBinder
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní váže pole symbolu, obvykle vrácený zprostředkovatelem symbol, k místní paměti nebo objekt, který obsahuje aktuální hodnotu tohoto symbolu.

## <a name="syntax"></a>Syntaxe

```
IDebugBinder : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní podporuje vyhodnocení výrazu a musí být implementované ladicího stroje (DE).

## <a name="notes-for-callers"></a>Poznámky pro volající
 Toto rozhraní se použije při vyhodnocení výrazu a obvykle se používá při provádění [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) a [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugBinder`.

|Metoda|Popis|
|------------|-----------------|
|[Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)|Získá kontext paměti nebo objekt, který obsahuje aktuální hodnotu tohoto symbolu.|
|[ResolveRuntimeType](../../../extensibility/debugger/reference/idebugbinder-resolveruntimetype.md)|Určuje typ run-time objekt.|
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugbinder-getmemorycontext.md)|Převede adresu umístění nebo paměti objektu kontextu paměti.|
|[GetFunctionObject](../../../extensibility/debugger/reference/idebugbinder-getfunctionobject.md)|Získá [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt použitý k vytvoření parametry funkce.|
|[ResolveDynamicType](../../../extensibility/debugger/reference/idebugbinder-resolvedynamictype.md)|Získá přesný typ proměnné.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní vrátí objekty, které jsou používány vyhodnocovací filtr výrazů ve stromech pro analýzu. Chyba při vyhodnocování výrazu analyzuje výraz pomocí poskytovatel symbolů se převést symboly ve výrazu na instance [IDebugField](../../../extensibility/debugger/reference/idebugfield.md), které popisují každý symbol z hlediska její typ a umístění ve zdrojovém kódu. [Svázat](../../../extensibility/debugger/reference/idebugbinder-bind.md) metoda převede `IDebugField` objektů [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) typ objektů, které se připojit nebo vytvořit vazbu symbol na skutečnou hodnotu v paměti. Tyto `IDebugObject` objekty jsou pak uloženy v strom analýzy pro pozdější vyhodnocení.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)
- [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)