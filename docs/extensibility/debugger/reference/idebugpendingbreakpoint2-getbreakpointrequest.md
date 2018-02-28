---
title: IDebugPendingBreakpoint2::GetBreakpointRequest | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPendingBreakpoint2::GetBreakpointRequest
helpviewer_keywords:
- IDebugPendingBreakpoint2::GetBreakpointRequest method
- GetBreakpointRequest method
ms.assetid: cb1e36aa-4302-455c-98fb-6638a1ef5c46
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0b868d3f5e108b517a6d9f182ba758ba78776486
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpendingbreakpoint2getbreakpointrequest"></a>IDebugPendingBreakpoint2::GetBreakpointRequest
Získá zarážek požadavek, který byl použit k vytvoření této čekající zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetBreakpointRequest(   
   IDebugBreakpointRequest2** ppBPRequest  
);  
```  
  
```csharp  
int GetBreakpointRequest(   
   out IDebugBreakpointRequest2 ppBPRequest  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppBPRequest`  
 [out] Vrátí [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) objekt reprezentující zarážek požadavek, který byl použit k vytvoření to čekající na vyřízení zarážek.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud zarážce byl odstraněn.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)