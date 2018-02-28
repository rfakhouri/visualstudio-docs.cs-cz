---
title: IDebugExpressionEvaluator3::Parse2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugExpressionEvaluator3::Parse2
ms.assetid: 78099628-d600-4f76-b7c8-ee07c864af1e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c4c5e2a62cfbe44fe6a68da703df6ff81a89d07e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluator3parse2"></a>IDebugExpressionEvaluator3::Parse2
Převede řetězec výraz výraz analyzovaný daného symbolu zprostředkovatele a adresu vyhodnocování rámce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 [v] Řetězec výraz, který se má analyzovat.  
  
 `dwFlags`  
 [v] Kolekce [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) konstanty, které určují, jak se výraz analyzovat.  
  
 `nRadix`  
 [v] Základ – který se má použít k interpretaci všechny číselné informace.  
  
 `pSymbolProvider`  
 [v] Rozhraní symbol zprostředkovatele.  
  
 `pAddress`  
 [v] Adresa vyhodnocování rámečku.  
  
 `pbstrError`  
 [out] Vrátí chybu jako čitelný text.  
  
 `pichError`  
 [out] Vrátí znak na pozici spouštění Chyba v řetězci výrazu.  
  
 `ppParsedExpression`  
 [out] Vrátí Analyzovaná výrazu v [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytváří výraz analyzovaný není skutečnou hodnotu. Analyzovaná výrazu je připraven k vyhodnocení, to znamená, převést na hodnotu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro tuto metodu implementovat **CEE** objekt, který zveřejňuje [IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md) rozhraní.  
  
```cpp  
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