---
title: IDebugProperty3::SetValueAsStringWithError | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::SetValueAsStringWithError
helpviewer_keywords:
- IDebugProperty3::SetValueAsStringWithError
ms.assetid: b378368f-4a45-4b2f-8e3d-3bff7a18ab17
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 61a39d3b68deec2dd51c49113355a8ed6c69325c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348820"
---
# <a name="idebugproperty3setvalueasstringwitherror"></a>IDebugProperty3::SetValueAsStringWithError
Nastaví hodnotu této vlastnosti a vrátí chybovou zprávu, pokud je to nutné.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValueAsStringWithError(
    LPCOLESTR pszValue,
    DWORD     dwRadix,
    DWORD     dwTimeout,
    BSTR*     errorString
);
```

```csharp
int SetValueAsStringWithError(
    string     pszValue,
    uint       dwRadix,
    uint       dwTimeout,
    out string errorString
);
```

## <a name="parameters"></a>Parametry
`pszValue`\
[in] Hodnota k nastavení.

`dwRadix`\
[in] Základ číselné soustavy nastaví se hodnota.

`dwTimeout`\
[in] Doba čekání nastavit hodnotu (`INFINITE` znamená, že stále čekat).

`errorString`\
[out] Pokud došlo k chybě, nastavením této hodnoty, to obsahuje příčinu selhání.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
Příchozí hodnotou může být výraz, který se má vyhodnotit.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak pro tuto metodu implementovat **CProperty** objekt, který zveřejňuje [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní.

```cpp
HRESULT CProperty::SetValueAsStringWithError(
    LPCOLESTR in_szValue,
    DWORD in_RADIX,
    DWORD in_TIMEOUT,
    BSTR * out_ERRORTEXT
)
{
    // precondition
    REQUIRE( NULL != in_szValue );

    if (NULL == in_szValue)
        return E_INVALIDARG;

    INVARIANT( this );
    if (!this->ClassInvariant())
        return E_UNEXPECTED;

    if (NULL == m_pPropertyContext->m_pCEE->m_LanguageSpecificUseCases.pfSetValue)
        return S_OK;

    // function body
    DEBUG_PROPERTY_INFO dpInfo,dpInfo2;
    HRESULT HR = this->GetPropertyInfo(DEBUGPROP_INFO_FULLNAME | DEBUGPROP_INFO_ATTRIB | DEBUGPROP_INFO_TYPE | DEBUGPROP_INFO_VALUE_AUTOEXPAND,
                                       in_RADIX,
                                       in_TIMEOUT,
                                       NULL,
                                       0,
                                       &dpInfo);

    if (ENSURE( S_OK == HR ))
    {
        REQUIRE( NULL != dpInfo.bstrFullName );
        REQUIRE( NULL != dpInfo.bstrType );

        REQUIRE( NULL == dpInfo.bstrName );
        REQUIRE( NULL == dpInfo.bstrValue );
        REQUIRE( NULL == dpInfo.pProperty );

        BSTR bstrError = NULL;

        UINT ichError = 0;
        IDebugProperty2* pProperty = NULL;
        IDebugParsedExpression* pParsedExpression = NULL;

        CComBSTR bstrValue = dpInfo.bstrFullName;
        bstrValue += L" = ";
        bstrValue += in_szValue;
        HR = this->m_pPropertyContext->m_pCEE->
                Parse(bstrValue, 0, in_RADIX, &bstrError, &ichError, &pParsedExpression);
        if (S_OK == HR)
        {
            REQUIRE( NULL == bstrError );
            HR = pParsedExpression->EvaluateSync(EVAL_NOEVENTS | EVAL_RETURNVALUE,
                                                 in_TIMEOUT,
                                                 m_pPropertyContext->m_pSymbolProvider,
                                                 m_pPropertyContext->m_pAddress,
                                                 m_pPropertyContext->m_pBinder,
                                                 NULL,
                                                 &pProperty);

            dpInfo2.dwAttrib = DBG_ATTRIB_VALUE_ERROR;
            if (pProperty)
            {
                pProperty->GetPropertyInfo(DEBUGPROP_INFO_ATTRIB | DEBUGPROP_INFO_VALUE,10,in_TIMEOUT,NULL,0,&dpInfo2);
            }
            if (DBG_ATTRIB_VALUE_ERROR & dpInfo2.dwAttrib)
            {
                HR = E_FAIL;
                bstrError = dpInfo2.bstrValue;
            }
            else
            {
                ::SysFreeString(dpInfo.bstrValue);
            }
            EXTERNAL_RELEASE(pProperty);
            EXTERNAL_RELEASE(pParsedExpression);
        }

        if (bstrError)
        {
            if(out_ERRORTEXT)
            {
                *out_ERRORTEXT = bstrError;
                bstrError = NULL;
            }
            else
            {
                ::SysFreeString(bstrError);
            }
        }
        ::SysFreeString(dpInfo.bstrFullName);
        ::SysFreeString(dpInfo.bstrType);
    }

    // postcondition
    INVARIANT( this );

    return HR;
}
```

## <a name="see-also"></a>Viz také:
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
