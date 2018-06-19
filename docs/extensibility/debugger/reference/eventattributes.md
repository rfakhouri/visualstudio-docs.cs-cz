---
title: EVENTATTRIBUTES | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 87d6a2176dcd3c4cf748549f94d071b181d0d14f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103926"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
Určuje atributy událostí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>Členové  
 EVENT_ASYNCHRONOUS  
 Označuje, že událost je asynchronní, a je potřeba žádné odpovědi na události.  
  
 EVENT_SYNCHRONOUS  
 Označuje, že událost je synchronní; odpověď prostřednictvím [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT_STOPPING  
 Označuje, že se jedná o zastavení událost. Musí být kombinován s buď `EVENT_ASYNCHRONOUS` nebo `EVENT_SYNCHRONOUS`.  
  
 EVENT_ASYNC_STOP  
 Označuje událost asynchronní zastavit. Aktuálně neexistuje žádná taková událost. Tento příznak je pouze zástupce.  
  
 EVENT_SYNC_STOP  
 Označuje synchronní zastavení událostí (kombinaci `EVENT_SYNCHRONOUS` a `EVENT_STOPPING`). Tato hodnota se používá modul ladění (DE) při odesílání událostí zastavit. Odpověď se provádí prostřednictvím volání [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [krok](../../../extensibility/debugger/reference/idebugprogram2-step.md), nebo [pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT_IMMEDIATE  
 Označuje událost, která je odeslána okamžitě a synchronně k prostředí IDE. Tento příznak se zkombinuje s další příznaky jako `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, nebo `EVENT_SYNC_STOP` označující typ události a fakt, že se označuje mechanismus odpověď (pokud existuje).  
  
 EVENT_EXPRESSION_EVALUATION  
 Událost je výsledkem vyhodnocení výrazu.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předávány v `dwAttrib` parametr [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metoda.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)