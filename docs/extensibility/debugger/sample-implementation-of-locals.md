---
title: Ukázkové implementace lokální proměnné | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], local variables
- expression evaluation, local variables
ms.assetid: 66a2e00a-f558-4e87-96b8-5ecf5509e04c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56ac92989abe929884ac029e3b9c9c7dafad5fd9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130476"
---
# <a name="sample-implementation-of-locals"></a>Ukázka implementace lokální proměnné
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Tady je přehled o tom, jak Visual Studio získává místní hodnoty pro metodu z vyhodnocovací filtr výrazů (EE):  
  
1.  Visual Studio volá stroje ladění (DE) [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) získat [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje všechny vlastnosti rámce zásobníku, včetně lokální.  
  
2.  `IDebugStackFrame2::GetDebugProperty` volání [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) získat objekt, který popisuje metodu v rámci kterého došlo k chybě zarážku. DE poskytuje symbol zprostředkovatele ([IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)), adresu ([IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)) a vazač ([IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)).  
  
3.  `IDebugExpressionEvaluator::GetMethodProperty` volání [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md) s zadaných `IDebugAddress` objekt, který chcete získat [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) představující metodu obsahující zadanou adresu.  
  
4.  `IDebugContainerField` Rozhraní je dotazován na [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) rozhraní. Je toto rozhraní, která poskytuje přístup k místní hodnoty – metody.  
  
5.  `IDebugExpressionEvaluator::GetMethodProperty` vytvoří instanci třídy (nazývá `CFieldProperty` v ukázce), která implementuje `IDebugProperty2` rozhraní představují místní hodnoty – metody. `IDebugMethodField` Objekt je umístěn v tomto `CFieldProperty` objektu spolu s `IDebugSymbolProvider`, `IDebugAddress` a `IDebugBinder` objekty.  
  
6.  Když `CFieldProperty` inicializaci objektu [GetInfo](../../extensibility/debugger/reference/idebugfield-getinfo.md) se volá na `IDebugMethodField` objekt, který chcete získat [FIELD_INFO](../../extensibility/debugger/reference/field-info.md) struktura, která obsahuje všechny zobrazitelné informace o metoda sama .  
  
7.  `IDebugExpressionEvaluator::GetMethodProperty` Vrátí `CFieldProperty` objekt jako `IDebugProperty2` objektu.  
  
8.  Visual Studio volání [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) na vrácený `IDebugProperty2` objekt s filtrem `guidFilterLocalsPlusArgs`. Vrátí [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objekt obsahující místní hodnoty – metody. Tento výčet je vyplněna objektem volání [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) a [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md).  
  
9. Visual Studio volání [Další](../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md) získat [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) strukturu pro každý místní. Tato struktura obsahuje odkazy `IDebugProperty2` rozhraní pro místní.  
  
10. Visual Studio volání [GetPropertyInfo –](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) pro každý místní získat název, hodnotu a typ místní. Toto je informace, které se zobrazí v **místní hodnoty –** okno.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Implementace GetMethodProperty](../../extensibility/debugger/implementing-getmethodproperty.md)  
 Popisuje implementace [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md).  
  
 [Vytváření výčtů pro místní hodnoty](../../extensibility/debugger/enumerating-locals.md)  
 Popisuje, jak modul ladění (DE) odešle volání na výčet lokální proměnné nebo argumenty.  
  
 [Načtení místních vlastností](../../extensibility/debugger/getting-local-properties.md)  
 Popisuje, jak je DE zavolá se získat název, typ a hodnotu jeden nebo více lokální proměnné.  
  
 [Načtení místních hodnot](../../extensibility/debugger/getting-local-values.md)  
 Popisuje, získávání hodnotu místní, který vyžaduje službu objektu vazač poskytují kontext vyhodnocení.  
  
 [Vyhodnocení místních hodnot](../../extensibility/debugger/evaluating-locals.md)  
 Vysvětluje, jak se vyhodnocují místní hodnoty.  
  
## <a name="related-sections"></a>Související oddíly  
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md)  
 Poskytuje argumenty, které se předá, když je DE volá vyhodnocovací filtr výrazů (EE).  
  
 [Ukázka MyCEE](http://msdn.microsoft.com/en-us/624a018b-9179-402f-9d48-3aec87b48f4f)  
 Ukazuje jeden ze způsobů implementace k vytvoření vyhodnocení výrazu pro jazyk MyC.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)