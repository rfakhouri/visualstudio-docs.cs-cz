---
title: IDebugFunctionObject2::Evaluate | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugFunctionObject2::Evaluate
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f785e698e0c73146e4b80838d815c300bffa7abc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53991214"
---
# <a name="idebugfunctionobject2evaluate"></a>IDebugFunctionObject2::Evaluate
Volá funkci a vrátí výslednou hodnotu jako objekt.  
  
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
 [in] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty, které představují vstupní parametry. Každý z těchto parametrů bylo vytvořeno s použitím jedné z metod vytvořit v tomto rozhraní.  
  
 `dwParams`  
 [in] Počet parametrů `ppParams` pole.  
  
 `dwEvalFlags`  
 [in] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet určující, jak se má provést vyhodnocení.  
  
 `dwTimeout`  
 [in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití **NEKONEČNÉ** čekat po neomezenou dobu.  
  
 `ppResult`  
 [out] Vrátí **IDebugObject** , který představuje hodnotu funkce jako objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)