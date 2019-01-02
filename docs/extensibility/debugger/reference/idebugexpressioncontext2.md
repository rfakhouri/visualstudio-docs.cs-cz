---
title: IDebugExpressionContext2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpressionContext2
helpviewer_keywords:
- IDebugExpressionContext2 interface
ms.assetid: 577fdaae-4b2d-4112-9839-ab899535fa6f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 836ff67b314265081a4dc47d4984c4e0ff35fcd7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959771"
---
# <a name="idebugexpressioncontext2"></a>IDebugExpressionContext2
Toto rozhraní představuje kontext pro vyhodnocení výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpressionContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní představující kontext, ve kterém můžete vyhodnotit výraz.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) vrátí tohoto rozhraní. Toto rozhraní je přístupný pouze v případě, že byl pozastaven laděnému programu a rámec zásobníku je k dispozici.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugExpressionContext2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugexpressioncontext2-getname.md)|Načte název kontext vyhodnocení.|  
|[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)|Analyzuje výrazu založený na textu pro hodnocení.|  
  
## <a name="remarks"></a>Poznámky  
 Objekt context hodnocení můžete představit jako obor pro provádění vyhodnocení výrazu.  
  
 Když program se zastavil, Správce ladění relace (SDM) získává rámec zásobníku z DE voláním [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md). Pak zavolá SDM [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) zobrazíte `IDebugExpressionContext2` rozhraní. Následuje volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) k vytvoření [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, které představuje analyzovaný výraz, který je připravený k vyhodnocení.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)