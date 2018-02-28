---
title: IDebugBoundBreakpoint2::SetHitCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 44393469852cc17c982e644433ba8f38af5f7aa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
Nastaví počet přístupů k vázané breakpoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetHitCount(   
   DWORD dwHitCount  
);  
```  
  
```csharp  
int SetHitCount(   
   uint dwHitCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwHitCount`  
 [v] Počet přístupů k nastavení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud je nastavena do stavu objektu vázané breakpoint `BPS_DELETED` (součást [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) výčet).  
  
## <a name="remarks"></a>Poznámky  
 Počet přístupů je počet, který se má tento zarážek aktivováno během aktuálního spuštění relace.  
  
 Tato metoda je volána obvykle modul ladění aktualizovat aktuální počet přístupů na této zarážky.  
  
## <a name="see-also"></a>Viz také  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)