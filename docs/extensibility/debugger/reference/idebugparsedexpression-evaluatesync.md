---
title: IDebugParsedExpression::EvaluateSync | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugParsedExpression::EvaluateSync
helpviewer_keywords: IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 261359ae3dc82f8544d0f48cf0e8f1103ccedd5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
Tato metoda vyhodnocuje Analyzovaná výraz a volitelně vrhá výsledek, který má jiný typ data.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EvaluateSync(   
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BSTR                  bstrResultType,  
   IDebugProperty2**     ppResult  
);  
```  
  
```csharp  
int EvaluateSync(  
   uint                 dwEvalFlags,   
   uint                 dwTimeout,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   string               bstrResultType,   
   out IDebugProperty2  ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwEvalFlags`  
 [v] Kombinace [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) konstanty, které řídí, jak se výraz vyhodnotí.  
  
 `dwTimeout`  
 [v] Určuje maximální dobu v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
 `pSymbolProvider`  
 [v] Symbol poskytovatele, vyjádřené jako [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) rozhraní.  
  
 `pAddress`  
 [v] Aktuální umístění spuštění v rámci metodu, vyjádřené jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
 `pBinder`  
 [v] Vazač, vyjádřené jako [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) rozhraní.  
  
 `bstrResultType`  
 [v] Typ výsledku by měl přetypovat. Tento argument může mít hodnotu null.  
  
 `ppResult`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní, které představuje výsledky hodnocení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext vyhodnocení výrazu je dán `pAddress`, které umožňuje určit obsahující metody a pak oborů použití jazyka pravidla k určení hodnoty symbolů ve výrazu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)