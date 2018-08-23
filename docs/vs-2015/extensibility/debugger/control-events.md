---
title: Řízení událostí | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ac93da53f21b56df38a6ad597d7c4911075a670
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673612"
---
# <a name="control-events"></a>Události ovládacích prvků
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [události ovládacích prvků](https://docs.microsoft.com/visualstudio/extensibility/debugger/control-events).  
  
Události musí odesílat během řízené provádění programu. Všechny události se odesílají pomocí [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) rozhraní a mají atributy, které vyžadují, abyste pro implementaci [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) metody.  
  
## <a name="additional-methods"></a>Další metody  
 Některé události vyžadovat provedení další metody, následujícím způsobem:  
  
-   Odesílání [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) rozhraní při inicializaci ladicího stroje (DE) je potřeba implementovat [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) metody.  
  
-   Řízení provádění vyžaduje implementaci těchto událostí ovládacích prvků, jako [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) a[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) rozhraní. **IDebugBreakEvent2** se vyžaduje jenom pro asynchronní konce.  
  
-   Krokování s vnořením do funkcí vyžaduje implementaci [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) rozhraní a její metody.  
  
 Události odvozený od zarážky vyžadují provádění [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md), [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), a [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) rozhraní, jakož i [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) a [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) metody.  
  
 Vyhodnocení výrazu asynchronní je potřeba implementovat [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) rozhraní a jeho [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [a GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) metody.  
  
 Synchronní události vyžadovat implementaci [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) metody.  
  
 Modul pro zápis výstupu styl řetězce, je nutné implementovat [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [Řízení provádění a vyhodnocení stavu](../../extensibility/debugger/execution-control-and-state-evaluation.md)

