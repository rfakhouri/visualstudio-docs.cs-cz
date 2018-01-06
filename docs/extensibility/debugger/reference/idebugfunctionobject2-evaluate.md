---
title: IDebugFunctionObject2::Evaluate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugFunctionObject2::Evaluate
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a77b00c8c12fb355d53cff0008e41217626b6f9b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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