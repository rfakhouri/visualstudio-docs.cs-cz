---
title: IDebugExpressionEvaluator::GetMethodProperty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpressionEvaluator::GetMethodProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodProperty method
ms.assetid: c394fe4d-eeb6-4feb-828c-098d84a6f1ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0569c3e6a3d79279533c1c1c6717e8e5c3ce059
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53820771"
---
# <a name="idebugexpressionevaluatorgetmethodproperty"></a>IDebugExpressionEvaluator::GetMethodProperty
Tato metoda načte objekt vlastnost, která obsahuje oknech místní hodnoty, argumentů a další vlastnosti metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMethodProperty(   
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BOOL                  fIncludeHiddenLocals,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodProperty(  
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   int                  fIncludeHiddenLocals,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pSymbolProvider`  
 [in] Poskytovatel symbolů se použije, vyjádřené jako [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) objektu.  
  
 `pAddress`  
 [in] Adresy v kódu, vyjádřené jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu, který by měly být opraveny na nejbližší obsahující funkci.  
  
 `pBinder`  
 [in] Vazač, který má být použit, vyjádřené jako [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) objektu.  
  
 `fIncludeHiddenLocals`  
 [in] Nenulová (`TRUE`) znamená, že chcete zahrnout skryté lokální; nula (`FALSE`) znamená, že chcete nechat si místní skryté hodnoty  
  
 `ppProperty`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který představuje metodu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Skrytý místní hodnoty jsou obvykle proměnné, které jsou generovány kompilátorem.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)