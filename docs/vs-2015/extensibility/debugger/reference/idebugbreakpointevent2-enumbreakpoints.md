---
title: IDebugBreakpointEvent2::EnumBreakpoints | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugBreakpointEvent2:::EnumBreakpoints
helpviewer_keywords:
- IDebugBreakpointEvent2:::EnumBreakpoints
ms.assetid: 606a9625-ee43-4e84-9a47-af9a50d2d005
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1cc88853e24a40908c82748e4a811f86a58a37db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627871"
---
# <a name="idebugbreakpointevent2enumbreakpoints"></a>IDebugBreakpointEvent2::EnumBreakpoints
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugBreakpointEvent2::EnumBreakpoints](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints).  
  
Vytvoří čítač pro všechny zarážky, které aktivuje na aktuální umístění v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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

