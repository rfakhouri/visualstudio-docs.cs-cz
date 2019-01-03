---
title: IDebugStackFrame2::GetThread | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame2::GetThread
helpviewer_keywords:
- IDebugStackFrame2::GetThread
ms.assetid: cbeef85b-3dd7-4f97-adc2-c4d197d979fc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7fe4a7f5ef0ad06777983a1760f933e78d963838
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990578"
---
# <a name="idebugstackframe2getthread"></a>IDebugStackFrame2::GetThread
Získá přidružený blok zásobníku vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetThread (   
   IDebugThread2** ppThread  
);  
```  
  
```csharp  
int GetThread (   
   out IDebugThread2 ppThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppThread`  
 [out] Vrátí [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákna.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)