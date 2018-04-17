---
title: Vyhodnocení výrazu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, watch expressions
- watch expressions
ms.assetid: 8317cd52-6fea-4e8f-a739-774dc06bd44b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5d86b94a457934547037f2428e6284f20de1660d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="evaluating-a-watch-expression"></a>Vyhodnocení výrazu
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Visual Studio je připraven k zobrazit hodnotu výrazu, zavolá [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) který volá [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). To vytváří [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objekt, který obsahuje hodnoty a typ výrazu.  
  
 V této implementaci `IDebugParsedExpression::EvaluateSync`, je výraz analyzovat a posoudit ve stejnou dobu. Tato implementace provede následující úlohy:  
  
1.  Analyzuje a vyhodnotí výraz k vytvoření obecné objekt, který uchovává hodnotu a jeho typu. V jazyce C#, to je reprezentována jako `object` při v jazyce C++ je reprezentováno jako `VARIANT`.  
  
2.  Vytvoří instanci třídy (nazývá `CValueProperty` v tomto příkladu), která implementuje `IDebugProperty2` rozhraní a ukládá ve třídě, hodnota, která má být vrácen.  
  
3.  Vrátí `IDebugProperty2` rozhraní z `CValueProperty` objektu.  
  
## <a name="managed-code"></a>Spravovaný kód  
 Toto je implementace `IDebugParsedExpression::EvaluateSync` ve spravovaném kódu. Pomocná metoda `Tokenize` analyzuje výraz do strom analýzy. Pomocné funkce `EvalToken` převádí na hodnotu tokenu. Pomocné funkce `FindTerm` rekurzivně prochází strom analýzy volání `EvalToken` pro každý uzel představující hodnotu a použije všechny operace (desetin) ve výrazu.  
  
```csharp  
namespace EEMC  
{  
    public class CParsedExpression : IDebugParsedExpression  
    {  
        public HRESULT EvaluateSync(  
            uint evalFlags,  
            uint timeout,  
            IDebugSymbolProvider provider,  
            IDebugAddress address,  
            IDebugBinder binder,  
            string resultType,  
            out IDebugProperty2 result)  
        {  
            HRESULT retval = COM.S_OK;  
            this.evalFlags = evalFlags;  
            this.timeout = timeout;  
            this.provider = provider;  
            this.address = address;  
            this.binder = binder;  
            this.resultType = resultType;  
  
            try  
            {  
                IDebugField field = null;  
                // Tokenize, then parse.  
                tokens = Tokenize(expression);  
                result = new CValueProperty(  
                             expression,  
                             (int) FindTerm(EvalToken(tokens[0], out field),1),  
                             field,  
                             binder);  
            }  
            catch (ParseException)  
            {  
                result = new CValueProperty(expression, "Huh?");  
                retval = COM.E_INVALIDARG;  
            }  
            return retval;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Nespravovaný kód  
 Toto je implementace `IDebugParsedExpression::EvaluateSync` v nespravovaném kódu. Pomocné funkce `Evaluate` analyzuje a vyhodnotí výraz, vrácení `VARIANT` podržíte výslednou hodnotu. Pomocné funkce `VariantValueToProperty` sad `VARIANT` do `CValueProperty` objektu.  
  
```  
[C++]  
STDMETHODIMP CParsedExpression::EvaluateSync(   
    in  DWORD                 evalFlags,  
    in  DWORD                 dwTimeout,  
    in  IDebugSymbolProvider* pprovider,  
    in  IDebugAddress*        paddress,  
    in  IDebugBinder*         pbinder,  
    in  BSTR                  bstrResultType,  
    out IDebugProperty2**     ppproperty )  
{  
    // dwTimeout parameter is ignored in this implementation.  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (paddress == NULL)  
        return E_INVALIDARG;  
  
    if (pbinder == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    VARIANT value;  
    BSTR    bstrErrorMessage = NULL;  
    hr = ::Evaluate( pprovider,  
                     paddress,  
                     pbinder,  
                     m_expr,  
                     &bstrErrorMessage,  
                     &value );  
    if (hr != S_OK)  
    {  
        if (bstrErrorMessage == NULL)  
            return hr;  
  
        //we can display better messages ourselves.  
        HRESULT hrLocal = S_OK;  
        VARIANT varType;  
        VARIANT varErrorMessage;  
  
        VariantInit( &varType );  
        VariantInit( &varErrorMessage );  
        varErrorMessage.vt      = VT_BSTR;  
        varErrorMessage.bstrVal = bstrErrorMessage;  
  
        CValueProperty* valueProperty = new CValueProperty();  
        if (valueProperty != NULL)  
        {  
            hrLocal = valueProperty->Init(m_expr, varType, varErrorMessage);  
            if (SUCCEEDED(hrLocal))   
            {  
                hrLocal = valueProperty->QueryInterface( IID_IDebugProperty2,  
                        reinterpret_cast<void**>(ppproperty) );  
            }  
        }  
  
        VariantClear(&varType);  
        VariantClear(&varErrorMessage); //frees BSTR  
        if (!valueProperty)  
            return hr;  
        valueProperty->Release();  
        if (FAILED(hrLocal))  
            return hr;  
    }  
    else  
    {  
        if (bstrErrorMessage != NULL)  
            SysFreeString(bstrErrorMessage);  
  
        hr = VariantValueToProperty( pprovider,  
                                     paddress,  
                                     pbinder,  
                                     m_radix,  
                                     m_expr,  
                                     value,  
                                     ppproperty );  
        VariantClear(&value);  
        if (FAILED(hr))  
            return hr;  
    }  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Vyhodnocení výrazu okno kukátka](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [Ukázková implementace vyhodnocení výrazu](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)