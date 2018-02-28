---
title: IDebugExpressionEvaluator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluator
helpviewer_keywords:
- IDebugExpressionEvaluator interface
ms.assetid: 0636d8c3-625a-49fa-94b6-516f22b7e1bc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e0dad3317c3566051144bb7f3c335be9574103c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluator"></a>IDebugExpressionEvaluator
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní představuje vyhodnocovací filtr výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpressionEvaluator : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocovací filtr výrazů musí toto rozhraní implementovat.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Pokud chcete získat toto rozhraní, vytváření instancí vyhodnocovací filtr výrazů prostřednictvím `CoCreateInstance` metoda pomocí třídu ID (CLSID) vyhodnocování. Podívejte se na příklad.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugExpressionEvaluator`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)|Převede řetězec výraz analyzovaný výrazu.|  
|[GetMethodProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md)|Získá místní proměnné, argumentů a další vlastnosti metody.|  
|[GetMethodLocationProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodlocationproperty.md)|Převede metoda umístění a posun na adresu paměti.|  
|[Setlocale –](../../../extensibility/debugger/reference/idebugexpressionevaluator-setlocale.md)|Určuje jazyk, který chcete použít k vytvoření tiskových výsledky.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugexpressionevaluator-setregistryroot.md)|Nastaví kořenový klíč registru. Slouží k ladění vedle sebe.|  
  
## <a name="remarks"></a>Poznámky  
 V typické situaci, modul ladění (DE) vytvoří vyhodnocovací filtr výrazů (EE) v důsledku volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md). Protože je DE nezná jazyk a dodavatele EE chce použít, je DE získá z registru CLSID EE ( [SDK pomocníci pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) funkce, `GetEEMetric`, pomáhá s Tento načítání).  
  
 Po vytvoření instance EE DE volá [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) analyzovat ve výrazu a uložit ho v [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objektu. Později volání [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) vyhodnotí výraz.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak vytvořit instanci vyhodnocovací filtr výrazů daného symbolu zprostředkovatele a adresu ve zdrojovém kódu. Tento příklad používá funkce, `GetEEMetric`, z [SDK pomocníci pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) knihovny, dbgmetric.lib.  
  
```cpp  
IDebugExpressionEvaluator GetExpressionEvaluator(IDebugSymbolProvider pSymbolProvider,  
                                                 IDebugAddress *pSourceAddress)  
{  
    // This is typically defined globally but is specified here just  
    // for this example.  
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";  
  
    IDebugExpressionEvaluator *pEE = NULL;  
    if (pSymbolProvider != NULL && pSourceAddress != NULL) {  
        HRESULT hr         = S_OK;  
        GUID  languageGuid = { 0 };  
        GUID  vendorGuid   = { 0 };  
  
        hr = pSymbolProvider->GetLanguage(pSourceAddress,  
                                          &languageGuid,  
                                          &vendorGuid);  
        if (SUCCEEDED(hr)) {  
            CLSID clsidEE      = { 0 };  
            CComPtr<IDebugExpressionEvaluator> spExpressionEvaluator;  
            // Get the expression evaluator's CLSID from the registry.  
            ::GetEEMetric(languageGuid,  
                          vendorGuid,  
                          metricCLSID,  
                          &clsidEE,  
                          strRegistrationRoot);  
            if (!IsEqualGUID(clsidEE,GUID_NULL)) {  
                // Instantiate the expression evaluator.  
                spExpressionEvaluator.CoCreateInstance(clsidEE);  
            }  
            if (spExpressionEvaluator != NULL) {  
                pEE = spExpressionEvaluator.Detach();  
            }  
        }  
    }  
    return pEE;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)