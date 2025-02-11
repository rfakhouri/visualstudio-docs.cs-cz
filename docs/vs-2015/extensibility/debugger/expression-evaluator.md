---
title: Vyhodnocovací filtr výrazů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 423df66e8bd6bc1257a32236aa4ffbb28b80d655
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152741"
---
# <a name="expression-evaluator"></a>Vyhodnocovač výrazů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vyhodnocení výrazu (EE) zkontrolujte syntaxi jazyka analyzovat a vyhodnocovat proměnné a výrazy v době běhu, což jim umožní zobrazit uživatelem při integrovaného vývojového prostředí je v režimu pozastavení.  
  
## <a name="using-expression-evaluators"></a>Pomocí vyhodnocovače výrazů  
 Výrazy se vytvářejí pomocí [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metodu následujícím způsobem:  
  
1. Ladicí stroj (DE) implementuje [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.  
  
2. Získá balíček ladění `IDebugExpressionContext2` objektu z [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní a pak zavolá `IDebugStackFrame2::ParseText` metoda ji, abyste získali [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objektu.  
  
3. Volání balíčku ladění [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) metoda nebo [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) k získání hodnoty výrazu. `IDebugExpression2::EvaluateAsync` je volána z příkazu/proměnných. Dalším komponentám uživatelského rozhraní volejte `IDebugExpression2::EvaluateSync`.  
  
4. Výsledek vyhodnocení výrazu je [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objektu, který obsahuje název, typ a hodnota výsledku vyhodnocení výrazu.  
  
   Při vyhodnocení výrazu EE vyžaduje informace ze zprostředkovatele součásti symbolu. Poskytovatel symbolů poskytuje symbolické informace slouží k identifikaci a pochopení analyzovaný výrazu.  
  
   Po dokončení vyhodnocení výrazu asynchronní asynchronní událost posílá DE prostřednictvím Správce ladění relace (SDM) upozornit rozhraní IDE, vyhodnocení výrazu je dokončena. Po dokončení vyhodnocení výrazu synchronní z volání se vrátí výsledek vyhodnocení `IDebugExpression2::EvaluateSync` metody.  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Ladicími stroji očekávat ke komunikaci s využitím rozhraní Common Language Runtime (CLR) vyhodnocovací filtr výrazů. V důsledku toho vyhodnocovače výrazů, který funguje s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladicí stroj musí podporovat CLR (Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí sady [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)]).  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)
