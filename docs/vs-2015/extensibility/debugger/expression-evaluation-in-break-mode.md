---
title: Vyhodnocení výrazu v režimu pozastavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 362e50e20519c358564d13ba169f706fe384ca5c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152762"
---
# <a name="expression-evaluation-in-break-mode"></a>Vyhodnocení výrazu v režimu přerušení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující část popisuje proces, který nastane, pokud je v režimu přerušení ladicího programu a musí provést vyhodnocení výrazu.  
  
## <a name="expression-evaluation-process"></a>Proces vyhodnocení výrazu  
 Toto jsou základní kroky při vyhodnocení výrazu:  
  
1. Správce ladění relace (SDM) volá [IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) získat rozhraní kontextu výrazu [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md).  
  
2. Pak zavolá SDM [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) s řetězcem, který se má analyzovat.  
  
3. Pokud ParseText nevrací hodnotu S_OK, vrátí se z důvodu chyby.  
  
     -jinak-  
  
     Pokud ParseText nevrátí hodnotu S_OK, SDM pak můžete volat buď [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) získat konečnou hodnotu z analyzovaného výrazu.  
  
    - V případě použití `IDebugExpression2::EvaluateSync`, daného zpětného volání rozhraní se používá ke komunikaci probíhající proces hodnocení. Konečná hodnota se vrátí v [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní.  
  
    - V případě použití `IDebugExpression2::EvaluateAsync`, daného zpětného volání rozhraní se používá ke komunikaci probíhající proces hodnocení. Po dokončení hodnocení EvaluateAsync odešle [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) rozhraní zpětného volání. S tímto rozhraním události konečnou hodnotu lze získat pomocí [GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md).  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)
