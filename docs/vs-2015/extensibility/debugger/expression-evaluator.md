---
title: Vyhodnocovací filtr výrazů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8856284869a256f9be08931b36db644621a3202d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668459"
---
# <a name="expression-evaluator"></a>Vyhodnocovač výrazů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vyhodnocovací filtr výrazů](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluator).  
  
Vyhodnocení výrazu (EE) zkontrolujte syntaxi jazyka analyzovat a vyhodnocovat proměnné a výrazy v době běhu, což jim umožní zobrazit uživatelem při integrovaného vývojového prostředí je v režimu pozastavení.  
  
## <a name="using-expression-evaluators"></a>Pomocí vyhodnocovače výrazů  
 Výrazy se vytvářejí pomocí [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metodu následujícím způsobem:  
  
1.  Ladicí stroj (DE) implementuje [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.  
  
2.  Získá balíček ladění `IDebugExpressionContext2` objektu z [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní a pak zavolá `IDebugStackFrame2::ParseText` metoda ji, abyste získali [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objektu.  
  
3.  Volání balíčku ladění [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) metoda nebo [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) k získání hodnoty výrazu. `IDebugExpression2::EvaluateAsync` je volána z příkazu/proměnných. Dalším komponentám uživatelského rozhraní volejte `IDebugExpression2::EvaluateSync`.  
  
4.  Výsledek vyhodnocení výrazu je [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objektu, který obsahuje název, typ a hodnota výsledku vyhodnocení výrazu.  
  
 Při vyhodnocení výrazu EE vyžaduje informace ze zprostředkovatele součásti symbolu. Poskytovatel symbolů poskytuje symbolické informace slouží k identifikaci a pochopení analyzovaný výrazu.  
  
 Po dokončení vyhodnocení výrazu asynchronní asynchronní událost posílá DE prostřednictvím Správce ladění relace (SDM) upozornit rozhraní IDE, vyhodnocení výrazu je dokončena. Po dokončení vyhodnocení výrazu synchronní z volání se vrátí výsledek vyhodnocení `IDebugExpression2::EvaluateSync` metody.  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Ladicími stroji očekávat ke komunikaci s využitím rozhraní Common Language Runtime (CLR) vyhodnocovací filtr výrazů. V důsledku toho vyhodnocovače výrazů, který funguje s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladicí stroj musí podporovat CLR (Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí sady [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)]).  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)

