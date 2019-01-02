---
title: IDebugBreakpointEvent2::EnumBreakpoints | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointEvent2:::EnumBreakpoints
helpviewer_keywords:
- IDebugBreakpointEvent2:::EnumBreakpoints
ms.assetid: 606a9625-ee43-4e84-9a47-af9a50d2d005
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bd7f82a50e8a0d4b17ec63204248ccb88544ba6c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868836"
---
# <a name="idebugbreakpointevent2enumbreakpoints"></a>IDebugBreakpointEvent2::EnumBreakpoints
Vytvoří čítač pro všechny zarážky, které aktivuje na aktuální umístění v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumBreakpoints(  
  IEnumDebugBoundBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int EnumBreakpoints(  
  out IEnumDebugBoundBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) objekt, který uvádí všechny zarážky, které jsou přidružené k aktuální umístění v kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Ne všechny zarážky v konkrétních místech může vyvolat v určitou dobu (například zarážky s podmínkou se neaktivují až do splnění této podmínky).  
  
## <a name="see-also"></a>Viz také  
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)   
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)