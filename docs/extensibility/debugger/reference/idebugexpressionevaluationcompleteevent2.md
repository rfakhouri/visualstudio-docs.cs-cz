---
title: IDebugExpressionEvaluationCompleteEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluationCompleteEvent2
helpviewer_keywords:
- IDebugExpressionEvaluationCompleteEvent2
ms.assetid: d538fc19-55bf-4231-9595-eb01e84fd1d8
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 42dfc3ed4a4bff3e0c32d7155a74d74c1c6d0503
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluationcompleteevent2"></a>IDebugExpressionEvaluationCompleteEvent2
Toto rozhraní zasílá modul ladění (DE) zadaný pro relaci ladění správce (SDM) po dokončení vyhodnocení asynchronní výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpressionEvaluationCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní k dokončení sestavy vyhodnocení výrazu spuštění voláním [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md). [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí k hlášení dokončení vyhodnocení výrazu. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při jej připojit k programu laděné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugExpressionEvaluationCompleteEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetExpression](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)|Získá původní výraz.|  
|[GetResult](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)|Získá výsledek vyhodnocení výrazu.|  
  
## <a name="remarks"></a>Poznámky  
 DE musí odeslat tuto událost, zda vyhodnocení proběhla úspěšně, či nikoli.  
  
 Pokud nebyla úspěšná, vyhodnocení `DEBUG_PROPINFO_VALUE` a `DEBUG_PROPINFO_ATTRIB` příznaky nenastaví [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktura, která je vrácena [GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) ( [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt vytvořený DE a vrátí `IDebugExpressionEvaluationCompleteEvent2` událost, pokud se nezdařilo vyhodnocení).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)