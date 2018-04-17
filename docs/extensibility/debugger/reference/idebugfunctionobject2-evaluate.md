---
title: IDebugFunctionObject2::Evaluate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugFunctionObject2::Evaluate
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8196eb45b2fe7eccbff5c23a7ffc58fd3eb59282
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugfunctionobject2evaluate"></a>IDebugFunctionObject2::Evaluate
Volání funkce a vrátí výslednou hodnotu jako objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Evaluate (  
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwEvalFlags,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate (  
   IDebugObject     ppParams,  
   uint             dwParams,  
   uint             dwEvalFlags,  
   uint             dwTimeout,  
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParams`  
 [v] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty, které představují vstupní parametry. Každý z těchto parametrů byl vytvořen pomocí jedné z metod vytvořit v tomto rozhraní.  
  
 `dwParams`  
 [v] Počet parametrů `ppParams` pole.  
  
 `dwEvalFlags`  
 [v] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet, který určit, jak má provést vyhodnocení.  
  
 `dwTimeout`  
 [v] Určuje maximální dobu v milisekundách pro čekání před návratem od této metody. Použití **NEKONEČNÉ** čekání po neomezenou dobu.  
  
 `ppResult`  
 [out] Vrátí **IDebugObject** představující hodnotu funkce jako objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)