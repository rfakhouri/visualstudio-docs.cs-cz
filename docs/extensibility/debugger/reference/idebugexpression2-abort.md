---
title: IDebugExpression2::Abort | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpression2::Abort
helpviewer_keywords:
- IDebugExpression2::Abort
ms.assetid: 4fcb712e-1bdb-4b75-a440-35cc79ee147e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 668b4fe87bb0c37796d63cb313c15d146c70a58e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53910591"
---
# <a name="idebugexpression2abort"></a>IDebugExpression2::Abort
Tato metoda zruší asynchronní výraz vyhodnocení jako tím, že volání [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Abort(  
   void  
);  
```  
  
```csharp  
int Abort();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Při vyhodnocení výrazu asynchronní zrušení, nebyla odeslána [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) události pro událost zpětného volání předána [připojit](../../../extensibility/debugger/reference/idebugprogram2-attach.md) nebo [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)