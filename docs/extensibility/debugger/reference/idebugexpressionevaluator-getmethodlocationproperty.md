---
title: IDebugExpressionEvaluator::GetMethodLocationProperty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f0c8778c512719302c90e1513575714d15105ccf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013805"
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
 [in] Metoda umístění a posun, vyjádřený jako řetězec.  
  
 `pSymbolProvider`  
 [in] Poskytovatel symbolů vyjádřený jako [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) objektu.  
  
 `pAddress`  
 [in] Adresy v rámci metody, vyjádřené jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu.  
  
 `pBinder`  
 [in] Vazač vyjádřený jako [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) objektu.  
  
 `ppProperty`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní, které představuje adresu paměti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vrácené adresu je možné nastavit zarážku, třeba.  
  
 Bez ohledu na název `upstrFullyQualifiedMethodPlusOffset`, tento parametr je možné předat název metody částečně kvalifikované. V takovém případě vybrané metody je ten, který obklopuje `pAddress`. Jak tento parametr je interpretován je až po implementaci vyhodnocovací filtr výrazů a jazyk, který podporuje.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)