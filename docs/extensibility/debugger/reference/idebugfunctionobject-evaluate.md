---
title: IDebugFunctionObject::Evaluate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionObject::Evaluate
helpviewer_keywords: IDebugFunctionObject::Evaluate method
ms.assetid: 29349ea3-d5c1-4135-aa76-ced073ab9683
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a665f5db26955db2d3879e0d37c07efd3856bf68
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectevaluate"></a>IDebugFunctionObject::Evaluate
Volání funkce a vrátí výslednou hodnotu jako objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Evaluate(   
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate(  
   IDebugObject[]   ppParams,   
   IntPtr           dwParams,   
   uint             dwTimeout,   
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParams`  
 [v] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty, které představují vstupní parametry. Každý z těchto parametrů byl vytvořen s jedním z `Create` metody v [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
 `dwParams`  
 [v] Počet parametrů `ppParams` pole.  
  
 `dwTimeout`  
 [v] Určuje maximální dobu v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
 `ppResult`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) představující hodnotu funkce jako objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda nastaví a provádí volání funkce reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)