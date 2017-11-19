---
title: "Vyhodnocovací filtr výrazů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b08da6a123107d793d522770d44315aaa432dede
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="expression-evaluator"></a>Vyhodnocení výrazu
Vyhodnocovače výrazů (EE) zkontrolujte syntaxi jazyka analyzovat a vyhodnocovat proměnné a výrazy v době běhu, což jim umožní jde zobrazit uživatele, když prostředí IDE je v režimu pozastavení.  
  
## <a name="using-expression-evaluators"></a>Pomocí vyhodnocovače výrazů  
 Výrazy se vytvářejí pomocí [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda následujícím způsobem:  
  
1.  Implementuje modul ladění (DE) [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.  
  
2.  Získá balíček ladění `IDebugExpressionContext2` objektu z [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní a pak zavolá `IDebugStackFrame2::ParseText` metoda na něm získat [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objektu.  
  
3.  Volání balíček ladění [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) metoda nebo [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) metoda má být získána hodnota výrazu. `IDebugExpression2::EvaluateAsync`je volána z okna příkazu/Immediate. Všechny ostatní součásti uživatelského rozhraní volání `IDebugExpression2::EvaluateSync`.  
  
4.  Výsledkem vyhodnocení výrazu je [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt, který obsahuje název, typ a hodnotu výsledkem vyhodnocení výrazu.  
  
 Při vyhodnocení výrazu EE vyžaduje informace z poskytovatele komponenty symbol. Zprostředkovatel symbol poskytuje symbolické informace, které slouží pro identifikaci a pochopení Analyzovaná výraz.  
  
 Po dokončení vyhodnocení výrazu asynchronní asynchronní události je odesílá DE prostřednictvím Správce ladicí relace (SDM) informuje rozhraní IDE, vyhodnocení výrazu je dokončena. Po dokončení vyhodnocení synchronní výrazu je výsledkem vyhodnocení vrácená z volání `IDebugExpression2::EvaluateSync` metoda.  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Moduly ladění očekávat komunikovat s vyhodnocovací filtr výrazů pomocí rozhraní Common Language Runtime (CLR). V důsledku toho vyhodnocení výrazu, funguje s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění moduly musí podporovat modulu CLR (Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí systému [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)]).  
  
## <a name="see-also"></a>Viz také  
 [Ladicí program komponenty](../../extensibility/debugger/debugger-components.md)