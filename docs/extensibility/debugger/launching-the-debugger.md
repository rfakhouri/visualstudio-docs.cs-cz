---
title: "Spuštění ladicího programu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 23fd772b74c4caafbde37541933c38e306f9dc75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="launching-the-debugger"></a>Spuštění ladicího programu
Spuštění ladicího programu vyžaduje odesílání správné pořadí metod a události s jejich správné atributy.  
  
## <a name="sequences-of-methods-and-events"></a>Pořadí metod a události  
  
1.  Správce ladicí relace (SDM) se nazývá výběrem **ladění** nabídky a pak vyberete **spustit**. V tématu [spuštění programu](../../extensibility/debugger/launching-a-program.md) Další informace.  
  
2.  Volání SDM [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda.  
  
3.  Na základě modelu procesu ladění modulu (DE), `IDebugProgramNodeAttach2::OnAttach` metoda vrátí jednu z následujících metod, které určuje, co se stane dále.  
  
     Pokud `S_FALSE` se vrátí, modul ladění (DE) se má načíst vyřešit virtuálního počítače.  
  
     -nebo-  
  
     Pokud `S_OK` se vrátí, DE, je možné načíst v procesu zprávy SDM. SDM potom provede následující úlohy:  
  
    1.  Volání [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) k načtení modulu informací DE.  
  
    2.  Vytvoří společně DE.  
  
    3.  Volání [připojit](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
4.  Odešle DE [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
5.  Odešle DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
6.  Odešle DE [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
7.  Odešle DE [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
8.  Odešle DE [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
## <a name="see-also"></a>Viz také  
 [Události volání ladicí program](../../extensibility/debugger/calling-debugger-events.md)   
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)