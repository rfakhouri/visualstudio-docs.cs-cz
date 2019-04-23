---
title: Spouští se ladicí program | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e9c57079246dd52bd7fb44371999d0c3747dad40
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083566"
---
# <a name="launching-the-debugger"></a>Spuštění ladicího programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Spouští se ladicí program vyžaduje odeslání tak správné pořadí metod a událostí pomocí jejich vlastních atributech.  
  
## <a name="sequences-of-methods-and-events"></a>Sekvence metody a události  
  
1. Správce ladění relace (SDM) se nazývá výběrem **ladění** nabídky a následným výběrem **Start**. Zobrazit [spuštění programu](../../extensibility/debugger/launching-a-program.md) Další informace.  
  
2. Volání SDM [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metody.  
  
3. Na základě modelu procesu ladicí stroj (DE), `IDebugProgramNodeAttach2::OnAttach` metoda vrátí jednu z následujících metod, které určuje, co bude dál.  
  
     Pokud `S_FALSE` se vrátí ladicí stroj (DE) je na načtení sledovaný virtuálního počítače.  
  
     -nebo-  
  
     Pokud `S_OK` se vrátí, DE má být načten v procesu z SDM. SDM potom provede následující úlohy:  
  
    1. Volání [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) získat informace pro modul DE.  
  
    2. Společně vytvoří DE.  
  
    3. Volání [připojit](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
4. Odešle DE [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
5. Odešle DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
6. Odešle DE [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
7. Odešle DE [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
8. Odešle DE [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)   
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)
