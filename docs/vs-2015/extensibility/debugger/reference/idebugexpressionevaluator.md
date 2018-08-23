---
title: IDebugExpressionEvaluator | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluator
helpviewer_keywords:
- IDebugExpressionEvaluator interface
ms.assetid: 0636d8c3-625a-49fa-94b6-516f22b7e1bc
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea4c6aa2a389ea16a45a36c66a2e95e05f955107
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633338"
---
# <a name="idebugexpressionevaluator"></a>IDebugExpressionEvaluator
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugExpressionEvaluator](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator).  
  
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní představuje vyhodnocovací filtr výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpressionEvaluator : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Chyba při vyhodnocování výrazu musí implementovat toto rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 K získání tohoto rozhraní vytvořit instanci vyhodnocovací filtr výrazů prostřednictvím `CoCreateInstance` metodu s použitím ID (CLSID) třídu Chyba při vyhodnocování. Podívejte se na příklad.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugExpressionEvaluator`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Analýzy](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)|Převede řetězec s výrazem na analyzovaný výrazu.|  
|[GetMethodProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md)|Získá místní proměnné, argumenty a další vlastnosti metody.|  
|[GetMethodLocationProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodlocationproperty.md)|Metoda umístění a posun převede adresu paměti.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugexpressionevaluator-setlocale.md)|Určuje, jaký jazyk se má použít k vytvoření tisknutelný výsledky.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugexpressionevaluator-setregistryroot.md)|Nastaví kořenový klíč registru. Používá se pro ladění vedle sebe.|  
  
## <a name="remarks"></a>Poznámky  
 V typické situace ladicího stroje (DE) vytvoří vyhodnocovací filtr výrazů (EE) jako výsledek volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md). Protože DE zná jazyk a dodavatele EE chce použít, DE získá z registru CLSID EE ( [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) funkci `GetEEMetric`, pomáhá s toto načtení).  
  
 Po vytvoření instance EE DE volá [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) parsovat výraz a uloží je do [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objektu. Později volání [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) vyhodnotí výraz.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak vytvořit instanci vyhodnocovací filtr výrazů daný poskytovatel symbolů a adresa ve zdrojovém kódu. Tento příklad používá funkci `GetEEMetric`, z [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) knihovny, dbgmetric.lib.  
  
```cpp#  
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
 [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)

