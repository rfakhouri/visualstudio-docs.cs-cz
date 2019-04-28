---
title: Kontext vyhodnocení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 273325b8263af6f3fbacb96ece0b1194e0d5850f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63411344"
---
# <a name="evaluation-context"></a>Kontext vyhodnocení
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [ukázka Chyba při vyhodnocování výrazu spravované](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Když ladicí stroj (DE) volá vyhodnocovací filtr výrazů (EE), tři argumenty, které jsou předány [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) kontext pro hledání a vyhodnocování symbolů, zjistit, jak je znázorněno v následující tabulce.

## <a name="arguments"></a>Arguments

|Argument|Popis|
|--------------|-----------------|
|`pSymbolProvider`|[IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) rozhraní, která určuje symbol obslužné rutiny (SH) se použije k určení symbolu.|
|`pAddress`|[IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) rozhraní, které určuje aktuální bod provádění. Toto rozhraní najde metody, která obsahuje kód, který se spouští.|
|`pBinder`|[IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) rozhraní, které najde, hodnotu a typ symbolu, jeho název.|

 `IDebugParsedExpression::EvaluateSync` Vrátí [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) představující výslednou hodnotu a její typ rozhraní.

## <a name="see-also"></a>Viz také:
- [Rozhraní vyhodnocovače klíčových výrazů](../../extensibility/debugger/key-expression-evaluator-interfaces.md)
- [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)
- [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)
- [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)