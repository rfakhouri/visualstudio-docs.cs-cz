---
title: Strategie implementace vyhodnocování výrazu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, implementation strategy
- debug engines, implementation strategies
ms.assetid: 1bccaeb3-8109-4128-ae79-16fd8fbbaaa2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e67b2496c2e30428cd4cc830526e53cf0cc61fdd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102431"
---
# <a name="expression-evaluator-implementation-strategy"></a>Strategie implementace vyhodnocování výrazu
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Jeden z přístupů k rychlému vytvoření (EE) vyhodnocovací filtr výrazů je nejdřív implementovat minimální nutné zobrazit místní proměnné v kódu **místní hodnoty –** okno. Je užitečné Pamatujte si, že každý řádek v **místní hodnoty –** okně se zobrazí název, typ a hodnotu místní proměnné a že všechny tři, jsou reprezentovány [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objektu. Název, typ a hodnotu místní proměnné nelze získat ze `IDebugProperty2` objekt voláním jeho [GetPropertyInfo –](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metoda. Další informace o tom, jak zobrazit místní proměnné v **místní hodnoty –** okně najdete v části [zobrazení místní hodnoty –](../../extensibility/debugger/displaying-locals.md).  
  
## <a name="discussion"></a>Diskusní  
 Pořadí možné implementace začíná implementace [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md). [Analyzovat](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) a [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) metody nutné k implementaci zobrazíte místní hodnoty. Volání metody `IDebugExpressionEvaluator::GetMethodProperty` vrátí `IDebugProperty2` objekt, který reprezentuje metodu: tedy [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) objektu. Metody sami se nezobrazují v **místní hodnoty –** okno.  
  
 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) vedle by měla být implementována metoda. Modul ladění (DE) volá tuto metodu za účelem získání seznamu místní proměnné a argumenty předáním `IDebugProperty2::EnumChildren` `guidFilter` argument `guidFilterLocalsPlusArgs`. `IDebugProperty2::EnumChildren` volání [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) a [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md), kombinace výsledky v jednom výčtu. V tématu [zobrazení místní hodnoty –](../../extensibility/debugger/displaying-locals.md) další podrobnosti.  
  
## <a name="see-also"></a>Viz také  
 [Implementace vyhodnocení výrazu](../../extensibility/debugger/implementing-an-expression-evaluator.md)   
 [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)