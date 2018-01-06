---
title: "Připojení a odpojení programu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a5b0783cd011c91b9592479c7b64c6cb6a1afaa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="attaching-and-detaching-to-a-program"></a>Připojení a odpojení programu
Připojení ladicí program vyžaduje odesílání správné pořadí metod a události se správné atributy.  
  
## <a name="sequence-of-methods-and-events"></a>Pořadí metod a události  
  
1.  Volá správce ladicí relace (SDM) [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda.  
  
     Na základě modelu procesu ladění modulu (DE), `IDebugProgramNodeAttach2::OnAttach` metoda vrátí jednu z následujících metod, které určuje, co se stane dále.  
  
     Pokud `S_FALSE` se vrátí, modul ladění úspěšně byla připojena k programu. Jinak [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána k dokončení procesu připojování.  
  
     Pokud `S_OK` se vrátí, DE, je možné načíst v rámci jednoho procesu jako SDM. SDM provede následující úlohy:  
  
    1.  Volání [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) k načtení modulu informací DE.  
  
    2.  Vytvoří společně DE.  
  
    3.  Volání [připojit](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
2.  Odešle DE [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
3.  Odešle DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
4.  Odešle DE [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) k SDM s `EVENT_SYNC_STOP` atribut.  
  
 Odpojování od programu je jednoduché, dvoustupňový proces, následujícím způsobem:  
  
1.  Volání SDM [odpojení](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
2.  Odešle DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)