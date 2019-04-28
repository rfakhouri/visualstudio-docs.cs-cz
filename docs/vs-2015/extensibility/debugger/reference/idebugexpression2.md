---
title: IDebugExpression2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugExpression2
helpviewer_keywords:
- IDebugExpression2 interface
ms.assetid: f5e4b124-1e30-47c8-a511-80084a02dba5
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ec8b26f422ca39b771a47f8eb60ee862d7d388f9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62568366"
---
# <a name="idebugexpression2"></a>IDebugExpression2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní představuje analyzovaný výraz připravené pro vazby a hodnocení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpression2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci výrazu analyzovaný připraven k vyhodnocení.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) vrátí toto rozhraní. [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) vrátí [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Tato rozhraní jsou přístupné pouze v případě, že byl pozastaven laděnému programu a rámec zásobníku je k dispozici.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugExpression2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|Tento výraz vyhodnotí asynchronně.|  
|[Abort](../../../extensibility/debugger/reference/idebugexpression2-abort.md)|Ukončí asynchronní výraz hodnocení.|  
|[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|Tento výraz vyhodnotí synchronně.|  
  
## <a name="remarks"></a>Poznámky  
 Když program se zastavil, Správce ladění relace (SDM) získává rámec zásobníku z DE voláním [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md). Pak zavolá SDM [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) zobrazíte [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Následuje volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) vytvořit `IDebugExpression2` rozhraní, které představuje analyzovaný výraz, který je připravený k vyhodnocení.  
  
 SDM zavolá buď [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) skutečně vyhodnotí výraz a hodnotu.  
  
 V implementaci `IDebugExpressionContext2::ParseText`, DE používá modelu COM `CoCreateInstance` funkci pro vytvoření instance vyhodnocovače výrazů a získat [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) rozhraní (podívejte se na příklad v `IDebugExpressionEvaluator` rozhraní). Pak zavolá DE [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) získat [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) rozhraní. Toto rozhraní se používá při provádění `IDebugExpression2::EvaluateSync` a `IDebugExpression2::EvaluateAsync` pro provedení vyhodnocení.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpression](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)
