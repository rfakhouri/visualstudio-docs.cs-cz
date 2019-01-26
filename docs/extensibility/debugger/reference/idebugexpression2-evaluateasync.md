---
title: IDebugExpression2::EvaluateAsync | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpression2::EvaluateAsync
helpviewer_keywords:
- IDebugExpression2::EvaluateAsync
ms.assetid: 848fe6cb-0759-42f2-890b-d2b551c527d6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cd01cb13b302269a3a6d91fda14713d8a1412a45
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070739"
---
# <a name="idebugexpression2evaluateasync"></a>IDebugExpression2::EvaluateAsync
Tato metoda asynchronně vyhodnotí výraz.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EvaluateAsync (   
   EVALFLAGS             dwFlags,  
   IDebugEventCallback2* pExprCallback  
);  
```  
  
```csharp  
int EvaluateAsync(  
   enum_EVALFLAGS       dwFlags,   
   IDebugEventCallback2 pExprCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFlags`  
 [in] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet, který řídí vyhodnocení výrazu.  
  
 `pExprCallback`  
 [in] Tento parametr je vždy hodnota null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Typické chybový kód je:  
  
|Chyba|Popis|  
|-----------|-----------------|  
|E_EVALUATE_BUSY_WITH_EVALUATION|Jiný výraz je právě vyhodnocována a vyhodnocení souběžných výrazu se nepodporuje.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda by měla vrátit okamžitě po zahájení jeho vyhodnocení výrazu. Při úspěšném vyhodnocení výrazu, [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) se musí odeslat na [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) události zpětného volání, jak prostřednictvím [připojit ](../../../extensibility/debugger/reference/idebugprogram2-attach.md) nebo [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CExpression` objekt, který implementuje [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) rozhraní.  
  
```cpp  
HRESULT CExpression::EvaluateAsync(EVALFLAGS dwFlags,  
                                   IDebugEventCallback2* pExprCallback)  
{  
    // Set the aborted state to FALSE  
    // in case the user tries to redo the evaluation after aborting.  
    m_bAborted = FALSE;  
    // Post the WM_EVAL_EXPR message in the message queue of the current thread.  
    // This starts the expression evaluation on a background thread.  
    PostThreadMessage(GetCurrentThreadId(), WM_EVAL_EXPR, 0, (LPARAM) this);  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)