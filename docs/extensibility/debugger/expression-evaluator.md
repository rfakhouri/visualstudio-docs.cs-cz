---
title: Vyhodnocovací filtr výrazů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expressions [Debugging SDK]
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c9f990225cbff539281122d21d4773f6611f694f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353775"
---
# <a name="expression-evaluator"></a>Chyba při vyhodnocování výrazu
Vyhodnocení výrazu (EE) zkontrolujte syntaxi jazyka analyzovat a vyhodnocovat proměnné a výrazy v době běhu, což jim umožní zobrazit uživatelem při integrovaného vývojového prostředí je v režimu pozastavení.

## <a name="use-expression-evaluators"></a>Použít vyhodnocovače výrazů
 Výrazy se vytvářejí pomocí [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metodu následujícím způsobem:

1. Ladicí stroj (DE) implementuje [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.

2. Získá balíček ladění `IDebugExpressionContext2` objektu z [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní a pak zavolá `IDebugStackFrame2::ParseText` metoda ji, abyste získali [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objektu.

3. Volání balíčku ladění [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) metoda nebo [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) k získání hodnoty výrazu. `IDebugExpression2::EvaluateAsync` je volána z příkazu/proměnných. Dalším komponentám uživatelského rozhraní volejte `IDebugExpression2::EvaluateSync`.

4. Výsledek vyhodnocení výrazu je [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objektu, který obsahuje název, typ a hodnota výsledku vyhodnocení výrazu.

   Při vyhodnocení výrazu EE vyžaduje informace ze zprostředkovatele součásti symbolu. Poskytovatel symbolů poskytuje symbolické informace slouží k identifikaci a pochopení analyzovaný výrazu.

   Po dokončení vyhodnocení výrazu asynchronní asynchronní událost posílá DE prostřednictvím Správce ladění relace (SDM) upozornit rozhraní IDE, vyhodnocení výrazu je dokončena. A z volání se potom vrátí výsledek vyhodnocení `IDebugExpression2::EvaluateSync` metody.

## <a name="implementation-notes"></a>Poznámky k implementaci
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ladicími stroji očekávat ke komunikaci s využitím rozhraní Common Language Runtime (CLR) vyhodnocovací filtr výrazů. V důsledku toho vyhodnocovače výrazů, který funguje s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí stroj musí podporovat CLR (Úplný seznam všech CLR ladění v rozhraní najdete v debugref.doc, která je součástí sady [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)]).

## <a name="see-also"></a>Viz také:
- [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)