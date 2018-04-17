---
title: IDebugExpressionEvaluator::GetMethodLocationProperty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f10a26eca06aed24d53b70cd406fe3f24e2fe898
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
Tato metoda převede metoda umístění a posun na adresu paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMethodLocationProperty(   
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodLocationProperty(  
   string               upstrFullyQualifiedMethodPlusOffset,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `upstrFullyQualifiedMethodPlusOffset`  
 [v] Metoda umístění a posun, vyjádřené jako řetězec.  
  
 `pSymbolProvider`  
 [v] Zprostředkovatel symbol vyjádřený jako [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) objektu.  
  
 `pAddress`  
 [v] Adresu v metodě, vyjádřené jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu.  
  
 `pBinder`  
 [v] Vazač vyjádřený jako [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) objektu.  
  
 `ppProperty`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní, které představuje adresu paměti.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vrácený adres slouží k nastavení boru přerušení, třeba.  
  
 Bez ohledu název `upstrFullyQualifiedMethodPlusOffset`, tento parametr lze předat název částečně kvalifikovaný metody. V takovém případě vybranou metodu je ta, která obklopuje `pAddress`. Jak tento parametr je interpretován závisí provádění vyhodnocovací filtr výrazů a jazyk, který podporuje.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)