---
title: "Vyhodnocení výrazu okno kukátka | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Watch window expressions
- Watch window, expressions
- expression evaluation, Watch window expressions
ms.assetid: b07e72c7-60d3-4b30-8e3f-6db83454c348
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fb109fd91e4c295bf372b14e26bc2a75c3be6b1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="evaluating-a-watch-window-expression"></a>Vyhodnocení výrazu okno kukátka
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Při spuštění, pozastavení, Visual Studio volá modul ladění (DE) k určení aktuální hodnota každý výraz ve svém seznamu sledovat. DE vyhodnocuje každý výraz pomocí (EE) vyhodnocovací filtr výrazů a zobrazí její hodnota v sadě Visual Studio **sledovat** okno.  
  
 Tady je přehled způsob vyhodnocení výrazu seznamu:  
  
1.  Visual Studio volání je DE [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) získat kontextu výraz, který slouží k vyhodnocení výrazů.  
  
2.  Pro každý výraz v seznamu sledování Visual Studio volá [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) k převedení výraz text do Analyzovaná výraz.  
  
3.  `IDebugExpressionContext2::ParseText`volání [analyzovat](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) provedete skutečné práci při analýze textu a produkty [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) objektu.  
  
4.  `IDebugExpressionContext2::ParseText`vytvoří [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objekt a PUT `IDebugParsedExpression` objektu do ní. Tento I`DebugExpression2` objektu je pak vrácen do sady Visual Studio.  
  
5.  Visual Studio volání [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) při vyhodnocování výrazu Analyzovaná.  
  
6.  `IDebugExpression2::EvaluateSync`předá volání [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) provedete skutečné vyhodnocení a vytvořit [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt, který je vrácen do sady Visual Studio.  
  
7.  Visual Studio volání [GetPropertyInfo –](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) získat hodnotu výrazu, který se následně zobrazí v seznamu sledování.  
  
## <a name="parse-then-evaluate"></a>Analyzovat a vyhodnocení  
 Vzhledem k tomu, že analýza složitý výraz může trvat déle než vyhodnocení, proces vyhodnocení výrazu je rozdělena na dva kroky: 1) analyzovat výraz a 2) vyhodnocování Analyzovaná výrazu. Tímto způsobem vyhodnocení může dojít, kolikrát, ale výraz musí být analyzovat pouze jednou. Zprostředkující Analyzovaná výrazu je vrácena z EE v [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) objekt, který je pak zapouzdřené a byla vrácena z DE jako [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objektu. `IDebugExpression` Objekt odkládat údaje všechny zkušební verze na `IDebugParsedExpression` objektu.  
  
> [!NOTE]
>  Není nutné pro EE řídit tento dvoukrokový proces, i když to; předpokládá Visual Studio EE můžete analyzovat a vyhodnocovat u nich v stejný krok při [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) nazývá (jedná se jak MyCEE ukázka funguje, třeba). Pokud váš jazyk mohl vytvořit složité výrazy, můžete oddělit krok analýzy z kroku vyhodnocení. Tím mnoho podívejte se na výrazy, se může zvýšit výkonu v ladicím programu sady Visual Studio jsou zobrazena.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ukázková implementace vyhodnocení výrazu](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)  
 Pomocí ukázkových MyCEE krok procesem vyhodnocení výrazu.  
  
 [Vyhodnocení výrazu kukátka](../../extensibility/debugger/evaluating-a-watch-expression.md)  
 Vysvětluje, co se stane po úspěšné výraz analýzy.  
  
## <a name="related-sections"></a>Související oddíly  
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md)  
 Poskytuje argumenty, které se předá, když modul ladění (DE) vyvolá vyhodnocovací filtr výrazů (EE).  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)