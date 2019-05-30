---
title: IDebugParsedExpression | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugParsedExpression
helpviewer_keywords:
- IDebugParsedExpression interface
ms.assetid: be6486ed-b070-4898-95b1-58581bcb4447
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c56c0547d348c4fb3de387ac0ffce465b7bf5e90
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311776"
---
# <a name="idebugparsedexpression"></a>IDebugParsedExpression
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní představuje analyzovaný připravený, který se má vyhodnotit výraz.

## <a name="syntax"></a>Syntaxe

```
IDebugParsedExpression : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocovače výrazů implementuje toto rozhraní k reprezentaci analyzovaný výraz, který je připravený pro hodnocení.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody `IDebugParsedExpression`.

|Metoda|Popis|
|------------|-----------------|
|[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)|Vyhodnotí výraz v analyzovaných dat.|

## <a name="remarks"></a>Poznámky
 Volající je připraven k vyhodnocení výrazu, zavolá [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) se vraťte [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) , který obsahuje výsledek hodnocení. Tento přístup dvojdílného k vyhodnocení, analýze a hodnocení, umožňuje analyzovaný výraz, který má být vyhodnocen více než jednou, obcházení časově náročný proces analýzy výraz.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)