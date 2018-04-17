---
title: IDebugProcessEx2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 479206b75325c1b7e6bba0e4cc4e9b53944d73d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
Toto rozhraní umožňuje relace ladění manager (SDM) oznámit proces, který se připojuje k nebo probíhá odpojování od proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje dodavatele vlastní port pro stejný objekt, jako [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) rozhraní za účelem:  
  
-   Podpora sledování relací, které jsou připojené k procesu  
  
-   Podpora automatického – připojené napříč více modulů ladění  
  
 Vlastní port dodavatele může toto rozhraní implementovat, pokud se vybere.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
  
-   Volání SDM [QueryInterface](/cpp/atl/queryinterface) na `IDebugProcess2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugProcessEx2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Attach](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|Informuje o proces relace je nyní ladění proces.|  
|[Detach](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|Informuje o proces relace je již ladění proces.|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|Přidá program uzlů pro seznam modulů ladění.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je privátní mezi SDM a proces.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)