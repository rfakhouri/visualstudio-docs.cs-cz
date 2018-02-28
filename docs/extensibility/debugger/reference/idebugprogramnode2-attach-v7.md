---
title: IDebugProgramNode2::Attach_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramNode2::Attach
helpviewer_keywords:
- IDebugProgramNode2::Attach_V7
- IDebugProgramNode2::Attach
ms.assetid: b5ffc736-efc7-4ca8-964d-5536ff891b0e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 56e86962c8aa56b787eaf88f627ee807d894872c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnode2attachv7"></a>IDebugProgramNode2::Attach_V7
ZASTARALÉ. NEPOUŽÍVEJTE.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach_V7 (   
   IDebugProgram2*       pMDMProgram,  
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason  
);  
```  
  
```csharp  
int Attach_V7 (   
   IDebugProgram2       pMDMProgram,  
   IDebugEventCallback2 pCallback,  
   uint                 dwReason  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMDMProgram`  
 [v] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, které představuje program, který chcete přiřadit.  
  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) rozhraní použité k odesílání událostí ladění na SDM.  
  
 `dwReason`  
 [v] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který určuje důvod pro připojení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Implementace musí vracet vždycky `E_NOTIMPL`.  
  
## <a name="remarks"></a>Poznámky  
  
> [!WARNING]
>  Od [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)], tato metoda se již nepoužívá a musí vracet vždycky `E_NOTIMPL`. Najdete v článku [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) rozhraní alternativní způsob, pokud je program uzlu označíte, nemůže být připojen ke nebo pokud uzel programu je jednoduše nastavení programu `GUID`. Jinak, implementovat [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda.  
  
## <a name="prior-to-visual-studio-2005"></a>Před sady Visual Studio 2005  
 Tato metoda musí být implementována pouze v případě, že je DE běží v adresním prostoru programu laděné. Jinak tato metoda by měla vrátit `S_FALSE`.  
  
 Když tato metoda je volána, musíte odeslat DE [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) objekt události, pokud nebyl odeslán již pro tuto instanci [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní, a taky [ IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) a [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) objektů událostí. [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) události objektu je poté odeslán, pokud `dwReason` parametr `ATTACH_REASON_LAUNCH`.  
  
 DE musí volat [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) metodu [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt poskytl [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) události objektu a uložit tento program GUID v instanci data `IDebugProgram2` implementované DE objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)   
 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)