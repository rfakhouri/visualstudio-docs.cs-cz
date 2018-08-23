---
title: IDebugExpressionEvaluator3::Parse2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugExpressionEvaluator3::Parse2
ms.assetid: 78099628-d600-4f76-b7c8-ee07c864af1e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 79dc8f28d101a2c7bdd9749dcd9b3dadb4204273
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672871"
---
# <a name="idebugexpressionevaluator3parse2"></a>IDebugExpressionEvaluator3::Parse2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugExpressionEvaluator3::Parse2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator3-parse2).  
  
Převede řetězec s výrazem na analyzovaný výrazem zadaným poskytovatel symbolů a adresu vyhodnocování rámce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Parse2 (  
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   IDebugSymbolProvider*    pSymbolProvider,  
   IDebugAddress*           pAddress,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
HRESULT Parse2 (  
   string                     upstrExpression,  
   enum_PARSEFLAGS            dwFlags,  
   uint                       nRadix,  
   IDebugSymbolProvider       pSymbolProvider,  
   IDebugAddress              pAddress,  
   out string                 pbstrError,  
   out uint                   pichError,  
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `upstrExpression`  
 [in] Řetězec výrazu, který má být analyzován.  
  
 `dwFlags`  
 [in] Kolekce [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) konstanty, které určují, jak má být analyzován výraz.  
  
 `nRadix`  
 [in] Základ, který se má použít pro interpretaci jakékoli číselné informace.  
  
 `pSymbolProvider`  
 [in] Rozhraní poskytovatele symbolů.  
  
 `pAddress`  
 [in] Adresa vyhodnocování rámce.  
  
 `pbstrError`  
 [out] Vrátí chybu jako čitelný text.  
  
 `pichError`  
 [out] Vrátí pozici znaku start Chyba v řetězci výraz.  
  
 `ppParsedExpression`  
 [out] Vrátí analyzovaný výrazu v [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytváří analyzovaný výrazu, nikoli skutečnou hodnotu. Analyzovaná výrazu je připraven k vyhodnocení, to znamená, převést na hodnotu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro tuto metodu implementovat **CEE** objekt, který zveřejňuje [IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md) rozhraní.  
  
```cpp#  
HRESULT CEE::Parse2 ( LPCOLESTR in_szExprText,  
  PARSEFLAGS in_FLAGS,  
  UINT in_RADIX,  
  IDebugSymbolProvider *pSymbolProvider,  
  IDebugAddress *pAddress,  
  BSTR* out_pbstrError,  
  UINT* inout_pichError,  
  IDebugParsedExpression** out_ppParsedExpression )  
{  
    // precondition  
    REQUIRE( NULL != in_szExprText );  
    //REQUIRE( NULL != out_pbstrError );  
    REQUIRE( NULL != inout_pichError );  
    REQUIRE( NULL != out_ppParsedExpression );  
  
    if (NULL == in_szExprText)  
        return E_INVALIDARG;  
  
    if (NULL == inout_pichError)  
        return E_POINTER;  
  
    if (NULL == out_ppParsedExpression)  
        return E_POINTER;  
  
    if (out_pbstrError)  
        *out_pbstrError = NULL;  
  
    *out_ppParsedExpression = NULL;  
  
    INVARIANT( this );  
  
    if (!this->ClassInvariant())  
        return E_UNEXPECTED;  
  
    // function body  
    EEDomain::fParseExpression DomainVal =  
    {  
        this,                   // CEE*  
        in_szExprText,          // LPCOLESTR  
        in_FLAGS,               // EVALFLAGS  
        in_RADIX,               // RADIX  
        out_pbstrError      ,   // BSTR*  
        inout_pichError,        // UINT*  
        pSymbolProvider,  
        out_ppParsedExpression  // Output  
    };  
  
    return (*m_LanguageSpecificUseCases.pfParseExpression)(DomainVal);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md)

