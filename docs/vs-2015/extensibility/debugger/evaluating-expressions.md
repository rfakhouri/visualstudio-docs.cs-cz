---
title: Vyhodnocení výrazů | Dokumentace Microsoftu
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
- expressions [Debugging SDK], evaluating
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5ccfcc80-dea5-48a1-8bae-6a26f8d3bc56
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c51cc08da8c71a2ac1f25d02461ea9c24797ebc3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669583"
---
# <a name="evaluating-expressions"></a>Vyhodnocování výrazů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vyhodnocování výrazů](https://docs.microsoft.com/visualstudio/extensibility/debugger/evaluating-expressions).  
  
Výrazy jsou vytvořeny z řetězce předáván z automatické hodnoty, kukátko, QuickWatch nebo příkazovém podokně. Při vyhodnocování výrazu generuje tisknutelný řetězec, který obsahuje název a typ proměnné nebo argumentu a jeho hodnotu. Tento řetězec se zobrazí v okně odpovídající integrovaného vývojového prostředí.  
  
## <a name="implementation"></a>Implementace  
 Pokud program byl zastaven na zarážce, jsou výrazy vyhodnocovány. Samotný výraz je reprezentován [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, které představuje analyzovaný výraz, který je připravený pro vazby a hodnocení v rámci kontextu vyhodnocení daného výrazu. Rámec zásobníku určuje kontext vyhodnocení výrazu, který ladicí stroj (DE) poskytuje implementací [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.  
  
 Zadaný řetězec uživatele a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní, můžete získat ladicí stroj (DE) [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní tím, že předáte řetězec uživatel, který má [ IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metody. Vrácené rozhraní IDebugExpression2 obsahuje analyzovaný výraz připravené pro hodnocení.  
  
 S `IDebugExpression2` rozhraní, DE můžete získat hodnotu výrazu prostřednictvím vyhodnocení výrazu synchronní nebo asynchronní, pomocí [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [IDebugExpression2:: EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md). Tuto hodnotu, spolu s názvem a typem proměnné nebo argumentu, je odeslána do integrovaného vývojového prostředí pro zobrazení. Hodnota, název a typ jsou reprezentovány [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní.  
  
 Chcete-li povolit vyhodnocení výrazu, musí implementovat Zavedenými [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Synchronní a asynchronní vyhodnocování vyžadují provádění [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)

