---
title: "Vyhodnocení výrazů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expressions [Debugging SDK], evaluating
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5ccfcc80-dea5-48a1-8bae-6a26f8d3bc56
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 24cc20166bad875dcaebbd5492a7fe8317539d47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="evaluating-expressions"></a>Vyhodnocení výrazů
Výrazy se vytvářejí z řetězců, které jsou předávány z automobily, sledování, QuickWatch nebo okamžitou windows. Při vyhodnocování výrazu generuje tisknutelná řetězec, který obsahuje název a typ proměnné nebo argument a jeho hodnotu. Tento řetězec se zobrazí v okně odpovídající IDE.  
  
## <a name="implementation"></a>Implementace  
 Když program přestal na zarážce se vyhodnotí výrazy. Je reprezentována samotného výrazu [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, což představuje Analyzovaná výraz, který je připravený pro vazby a vyhodnocování v rámci kontext vyhodnocení daného výrazu. Kontext vyhodnocení výrazu, který poskytuje modul ladění (DE) implementací určuje rámce zásobníku [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.  
  
 Zadaný řetězec uživatele a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní, můžete získat modul ladění (DE) [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní předáním uživatele řetězec, který má [ IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda. Rozhraní IDebugExpression2 vrátil obsahuje analyzované výraz připraveno k vyhodnocení.  
  
 Pomocí `IDebugExpression2` rozhraní, DE můžete získat hodnotu výrazu prostřednictvím vyhodnocení výrazů synchronní nebo asynchronní, pomocí [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [IDebugExpression2:: EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md). Tato hodnota, společně s název a typ proměnné nebo argument, je odeslán rozhraní IDE pro zobrazení. Hodnota, název a typ jsou reprezentované pomocí [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní.  
  
 Pokud chcete povolit vyhodnocení výrazu, musí implementovat Zavedenými [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Synchronní a asynchronní vyhodnocení vyžadují provádění [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)