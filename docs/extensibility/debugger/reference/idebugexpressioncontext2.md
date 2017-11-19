---
title: IDebugExpressionContext2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExpressionContext2
helpviewer_keywords: IDebugExpressionContext2 interface
ms.assetid: 577fdaae-4b2d-4112-9839-ab899535fa6f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cfeede9a99a31acefb5fdf34afd8d6258c9f1019
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexpressioncontext2"></a>IDebugExpressionContext2
Toto rozhraní představuje kontext pro vyhodnocení výrazu  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpressionContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představující kontext, ve kterém lze výraz vyhodnotit.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) vrátí toto rozhraní. Toto rozhraní je dostupné jenom v případě, že byla pozastavena programu laděné a rámce zásobníku je k dispozici.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugExpressionContext2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetName –](../../../extensibility/debugger/reference/idebugexpressioncontext2-getname.md)|Načte název kontext vyhodnocení.|  
|[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)|Analyzuje výraz založený na textu pro vyhodnocení.|  
  
## <a name="remarks"></a>Poznámky  
 Kontext vyhodnocení můžete představit jako obor pro provádění vyhodnocení výrazu.  
  
 Když program se zastavil, správce ladicí relace (SDM) získává rámce zásobníku z DE pomocí volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md). Pak zavolá SDM [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) získat `IDebugExpressionContext2` rozhraní. Následují volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) vytvořit [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, což představuje Analyzovaná výraz, který je připraven k vyhodnocení.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)