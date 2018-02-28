---
title: "Podporované typy událostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], supported events
ms.assetid: a3c0386d-551e-4734-9a0c-368d1c2e6671
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d161b078e4001ea7f02311bbcefe4c7f1eb6b7b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="supported-event-types"></a>Typy podporované událostí
Visual Studio ladění aktuálně podporuje následující typy událostí:  
  
-   Asynchronní události  
  
     Oznámit správce ladicí relace (SDM) a rozhraní IDE, že je změna stavu laděné aplikace. Tyto události jsou zpracovávány ve volném čase SDM a rozhraní IDE. K modulu ladění (DE) je odeslána žádná odpověď, po zpracování události. [IDebugOutputStringEvent2](../../extensibility/debugger/reference/idebugoutputstringevent2.md) a [IDebugMessageEvent2](../../extensibility/debugger/reference/idebugmessageevent2.md) rozhraní jsou příklady asynchronní události.  
  
-   Synchronní události  
  
     Oznámit SDM a IDE, že je změna stavu laděné aplikace. Jediným rozdílem mezi tyto události a asynchronní události je, že se neodesílají na odpověď prostřednictvím [ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) metoda.  
  
     Odesílání synchronní události je užitečné, pokud je třeba vaše DE pokračovat zpracování po IDE přijímá a zpracovává událost.  
  
-   Synchronní zastavení události nebo zastavení události  
  
     Oznámit SDM a rozhraní IDE laděné aplikace byla zastavena provádění kódu. Při odesílání událostí zastavení prostřednictvím metody [událostí](../../extensibility/debugger/reference/idebugeventcallback2-event.md), [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) parametr je povinný. Ukončení události pocházejí voláním jeden z následujících metod:  
  
    -   [Spuštění](../../extensibility/debugger/reference/idebugprogram2-execute.md)  
  
    -   [Krok](../../extensibility/debugger/reference/idebugprogram2-step.md)  
  
    -   [Pokračovat](../../extensibility/debugger/reference/idebugprogram2-continue.md)  
  
     Rozhraní [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) a [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) jsou příklady zastavení události.  
  
    > [!NOTE]
    >  Asynchronní zastavení události nejsou podporovány. Jedná se o chybu pro odeslání události asynchronní zastavit.  
  
## <a name="discussion"></a>Diskusní  
 Skutečná implementace událostí závisí na návrh vašeho DE. Typ jednotlivých událostí odeslaných je dáno jeho atributy, které lze nastavit při návrhu DE. Například může odeslat jeden DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) jako asynchronní události, zatímco jiné může odesílat jako událost zastavit.  
  
 Následující tabulka určuje, které program a přístup z více vláken parametry jsou povinné, pro které události, stejně jako typy událostí. Všechny události může být synchronní. Žádné události musí být synchronní.  
  
> [!NOTE]
>  [IDebugEngine2](../../extensibility/debugger/reference/idebugengine2.md) rozhraní je vyžadována pro všechny události.  
  
|Událost|IDebugProgram2|IDebugThread2|Zastavení události|  
|-----------|--------------------|-------------------|---------------------|  
|[IDebugActivateDocumentEvent2](../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugBreakpointUnboundEvent2](../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugCanStopEvent2](../../extensibility/debugger/reference/idebugcanstopevent2.md)|Požadováno|Požadováno|Ne|  
|[IDebugDocumentTextEvents2](../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|Není povoleno|Není povoleno|Ne|  
|[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)|Není povoleno|Není povoleno|Ne|  
|[IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugErrorEvent2](../../extensibility/debugger/reference/idebugerrorevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Může být|  
|[IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Může být|  
|[IDebugInterceptExceptionCompleteEvent2](../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugMessageEvent2](../../extensibility/debugger/reference/idebugmessageevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Může být|  
|[IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|Požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugOutputStringEvent2](../../extensibility/debugger/reference/idebugoutputstringevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|Požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|Požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugPropertyCreateEvent2](../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|Požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugPropertyDestroyEvent2](../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|Požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugReturnValueEvent2](../../extensibility/debugger/reference/idebugreturnvalueevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|IDebugStopCompleteEvent2|Požadováno|Požadováno|Ano|  
|[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)|Požadováno|Požadováno|Ano|  
|[IDebugSymbolSearchEvent2](../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
|[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|Požadováno|Požadováno|Ne|  
|[IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|Požadováno|Požadováno|Ne|  
|[IDebugThreadNameChangedEvent2](../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|Povolené, ale není požadováno|Povolené, ale není požadováno|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Odesílání událostí](../../extensibility/debugger/sending-events.md)