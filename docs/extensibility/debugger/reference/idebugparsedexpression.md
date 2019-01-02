---
title: IDebugParsedExpression | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugParsedExpression
helpviewer_keywords:
- IDebugParsedExpression interface
ms.assetid: be6486ed-b070-4898-95b1-58581bcb4447
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: eaf70cd20982f4c3f2ec469bcce798142caee287
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53819496"
---
# <a name="idebugparsedexpression"></a>IDebugParsedExpression
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní představuje analyzovaný připravený, který se má vyhodnotit výraz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugParsedExpression : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocovače výrazů implementuje toto rozhraní k reprezentaci analyzovaný výraz, který je připravený pro hodnocení.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody `IDebugParsedExpression`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)|Vyhodnotí výraz v analyzovaných dat.|  
  
## <a name="remarks"></a>Poznámky  
 Volající je připraven k vyhodnocení výrazu, zavolá [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) se vraťte [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) , který obsahuje výsledek hodnocení. Tento přístup dvojdílného k vyhodnocení, analýze a hodnocení, umožňuje analyzovaný výraz, který má být vyhodnocen více než jednou, obcházení časově náročný proces analýzy výraz.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Analýzy](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)