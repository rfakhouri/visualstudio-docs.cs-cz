---
title: IDebugProperty2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2
helpviewer_keywords: IDebugProperty2 interface
ms.assetid: a7d5c70f-a1a5-4120-9f70-184e01c25bff
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 45ad3a6c0d250136d0ab3e1becb088ea140b42e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty2"></a>IDebugProperty2
Toto rozhraní představuje vlastnost rámce zásobníku, vlastnost dokumentu programu nebo některé jiné vlastnosti. Vlastnost je obvykle výsledkem vyhodnocení výrazu.  
  
> [!NOTE]
>  Toto použití "vlastnosti" by neměl Nezaměňovat s znamená členské proměnné třídy, i když `IDebugProperty2` může představovat taková entita.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProperty2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní představují konkrétní typ hodnoty. Hodnota může být například číselnou hodnotu výsledkem vyhodnocení výrazu, kontextu paměť použitá pro zobrazení paměti nebo seznam registry a jejich hodnoty.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) získat toto rozhraní, která reprezentuje výsledek zkušební verzi. `IDebugExpression2::EvaluateAsync`Vrátí toto rozhraní odesláním [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) rozhraní SDM, které volá [GetResult](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) načíst vlastnost.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md) vrátí toto rozhraní zajistit dokumentu přidružené skriptu.  
  
 [GetReturnValue](../../../extensibility/debugger/reference/idebugreturnvalueevent2-getreturnvalue.md) vrátí toto rozhraní představující vrácenou hodnotu funkce.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugprogram2-getdebugproperty.md) vrátí toto rozhraní představují různé vlastnosti programu, například název nebo kontextu paměti.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) vrátí toto rozhraní představují různé vlastnosti rámce zásobníku například místní proměnné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugProperty2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)|Vyplní [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktura, která popisuje vlastnosti.|  
|[SetValueAsString](../../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md)|Nastaví hodnotu vlastnosti z řetězce.|  
|[SetValueAsReference](../../../extensibility/debugger/reference/idebugproperty2-setvalueasreference.md)|Nastaví hodnotu vlastnosti z hodnoty danému odkazu.|  
|[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)|Vytvoří výčet podřízené objekty vlastnosti.|  
|[Getparent –](../../../extensibility/debugger/reference/idebugproperty2-getparent.md)|Vrací nadřazeného vlastnosti.|  
|[GetDerivedMostProperty](../../../extensibility/debugger/reference/idebugproperty2-getderivedmostproperty.md)|Vrátí vlastnosti, která popisuje vlastnosti většinou odvozených vlastnosti.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)|Vrátí bajtů paměti, které tvoří hodnotu vlastnosti.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)|Vrátí kontext paměti pro hodnotu vlastnosti.|  
|[Getsize –](../../../extensibility/debugger/reference/idebugproperty2-getsize.md)|Vrátí velikost v bajtech hodnoty vlastnosti.|  
|[Getreference –](../../../extensibility/debugger/reference/idebugproperty2-getreference.md)|Vrátí odkaz na tato vlastnost hodnotu.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md)|Vrátí rozšířené informace o vlastnosti.|  
  
## <a name="remarks"></a>Poznámky  
 Vlastnost, reprezentovaná `IDebugProperty2` rozhraní, můžete představit jako hodnotu s název, typ a adresu. V další obecné podmínky `IDebugProperty2` může představovat všechno, co má hierarchická struktura, s nadřazené a podřízené uzly.  
  
 Vlastnost se obvykle přechodné, například trvající pouze stejně dlouho jako aktuální rámec zásobníku. Na druhé straně odkaz, reprezentovaná [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) rozhraní, vydrží, dokud hodnota zůstane v paměti.  
  
 Můžete použít rozhraní IDE `IDebugProperty2` rozhraní tak, aby uživatelé procházet a úpravy vlastností v době běhu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)