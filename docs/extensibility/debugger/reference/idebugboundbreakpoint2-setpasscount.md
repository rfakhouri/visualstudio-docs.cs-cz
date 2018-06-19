---
title: IDebugBoundBreakpoint2::SetPassCount | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBoundBreakpoint2::SetPassCount
helpviewer_keywords:
- SetPassCount method
- IDebugBoundBreakpoint2::SetPassCount method
ms.assetid: b32c12f9-b34d-43bd-a1b9-61af6cf8e51b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 589792a9309565496b4d1ab73e1867055bcdf3bc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101235"
---
# <a name="idebugboundbreakpoint2setpasscount"></a>IDebugBoundBreakpoint2::SetPassCount
Nastaví nebo změny přidružené k této vázané Breakpoint – počet průchodu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetPassCount(   
   BP_PASSCOUNT bpPassCount  
);  
```  
  
```csharp  
int SetPassCount(   
   BP_PASSCOUNT bpPassCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bpPassCount`  
 [v] [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) struktura, která určuje počet průchodu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud je nastavena do stavu objektu vázané breakpoint `BPS_DELETED` (součást [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) výčet).  
  
## <a name="remarks"></a>Poznámky  
 Počet průchodu Určuje, když je aktivována, zarážku. Můžete získat aktuální průchod nebo počet přístupů voláním [GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md) metoda.  
  
 Libovolným počtem pass, který byl dříve přidružený tento zarážek bude ztracena.  
  
## <a name="see-also"></a>Viz také  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)