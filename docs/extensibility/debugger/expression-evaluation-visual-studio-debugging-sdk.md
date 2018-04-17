---
title: Vyhodnocení výrazu (Visual Studio ladění SDK) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5044ced5-c18c-4534-b0bf-cc3e50cd57ac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 022a0ee21b7a58fdd69249b240490fc3c1df8361
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="expression-evaluation-visual-studio-debugging-sdk"></a>Vyhodnocení výrazu (Visual Studio ladění SDK)
Během režimu pozastavení musí být schopen vyhodnotit jednoduché výrazy zahrnující několik proměnné vašeho programu rozhraní IDE. K tomu, musí být schopen analyzovat a vyhodnocovat u nich výraz, který jste zadali do jednoho okna IDE modul ladění (DE).  
  
 Výrazy se vytvářejí pomocí [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda a jsou reprezentována výsledná [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní.  
  
 **IDebugExpression2** rozhraní je implementováno modulem DE a volání jeho **EvalAsync** metodu pro návrat [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní IDE, aby bylo možné zobrazit výsledky vyhodnocení výrazu v prostředí IDE. [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) vrátí strukturu, která umožňuje umístit hodnotu výrazu do okna Sledování nebo do místní hodnoty – okno.  
  
 Ladění balíček nebo relace ladění správce (SDM) volá [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) nebo [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) získat [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní, které představuje Výsledek vyhodnocení. `IDebugProperty2` obsahuje metody, které vrací název, typ a hodnotu výrazu. Tyto informace se zobrazí v různých ladicího programu.  
  
## <a name="using-expression-evaluation"></a>Pomocí vyhodnocení výrazu  
 Pokud chcete použít vyhodnocení výrazu, je nutné implementovat [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda a všechny metody [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, jak je znázorněno v následující tabulce.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|Vyhodnotí výraz asynchronně.|  
|[Přerušení](../../extensibility/debugger/reference/idebugexpression2-abort.md)|Ukončí asynchronní výraz vyhodnocení.|  
|[EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|Vyhodnotí výraz synchronně.|  
  
 Synchronní a asynchronní vyhodnocení vyžadují provádění [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metoda. Vyhodnocení výrazu asynchronní vyžaduje implementace [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md).  
  
## <a name="see-also"></a>Viz také  
 [Řízení provádění a vyhodnocení stavu](../../extensibility/debugger/execution-control-and-state-evaluation.md)