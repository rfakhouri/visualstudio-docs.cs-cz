---
title: "Vyhodnocení výrazu v režimu pozastavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 766f00475971da1ca009737f9360952422177814
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="expression-evaluation-in-break-mode"></a>Vyhodnocení výrazu v režimu pozastavení
Následující část popisuje proces, který nastane, když je v režimu pozastavení ladicího programu a musí provést vyhodnocení výrazu.  
  
## <a name="expression-evaluation-process"></a>Proces vyhodnocení výrazu  
 Toto jsou základní kroky při vyhodnocování výrazu:  
  
1.  Volá správce ladicí relace (SDM) [IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) získat rozhraní kontextu výrazu [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md).  
  
2.  Pak zavolá SDM [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) s řetězec, který má být analyzován.  
  
3.  Pokud ParseText nevrací S_OK, vrátí se z důvodu chyby.  
  
     -jinak-  
  
     Pokud ParseText nevrátí S_OK, SDM můžete pak volat buď [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) získat konečná hodnota z analyzovaných výraz.  
  
    -   V případě použití `IDebugExpression2::EvaluateSync`, rozhraní daného zpětné volání se používá pro komunikaci probíhající proces hodnocení. Konečná hodnota je vrácený v [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní.  
  
    -   V případě použití `IDebugExpression2::EvaluateAsync`, rozhraní daného zpětné volání se používá pro komunikaci probíhající proces hodnocení. Po dokončení vyhodnocení EvaluateAsync odešle [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) rozhraní prostřednictvím zpětné volání. S tímto rozhraním událostí nelze získat konečná hodnota s [GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md).  
  
## <a name="see-also"></a>Viz také  
 [Události volání ladicí program](../../extensibility/debugger/calling-debugger-events.md)