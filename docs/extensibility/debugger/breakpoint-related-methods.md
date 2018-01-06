---
title: "Breakpoint – související metody | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], breakpoint methods
- breakpoints, methods
ms.assetid: a6f77bf0-bf81-443f-8683-5f12075bbe10
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f5bf80b78545242a625b9c3e212c101712ecbd9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="breakpoint-related-methods"></a>Breakpoint – související metody
Modul ladění (DE) musí podporovat nastavení zarážky. Visual Studio ladění podporuje následující typy zarážky:  
  
-   Vázaný  
  
     Požadovaný přes uživatelské rozhraní a úspěšně vázaný k umístění zadaný kód  
  
-   Čekající na vyřízení  
  
     Požadovaný prostřednictvím uživatelského rozhraní, ale není ještě vázaná na skutečné pokyny  
  
## <a name="discussion"></a>Diskusní  
 Například čekající zarážek nastane, když pokynů nebyly dosud načteny. Pokud kód je načtena, čekající na vyřízení zarážky zkuste vytvořit vazbu na kód v předepsané umístění, který je můžete vložit zalomení pokyny v kódu. Události se posílají správce ladicí relace (SDM) označuje úspěšné vazby a oznámit, že došlo k chybám vazby.  
  
 Čekající zarážek také spravuje vlastní interní seznam odpovídající vázané zarážky. Jedno čekající zarážek může způsobit vkládání mnoho zarážky v kódu. Ladění uživatelského rozhraní sady Visual Studio zobrazí stromové zobrazení čekající na vyřízení zarážky a jejich odpovídajících vázaný zarážky.  
  
 Vytvoření a použití čekající na vyřízení zarážky vyžadují implementace [IDebugEngine2::CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) metoda, jakož i tyto metody [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|Určuje, zda je zadané čekající na vyřízení zarážek můžete vázat na umístění kódu.|  
|[Vazby](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|Váže zadanou čekající na vyřízení zarážek jedno nebo více umístění kódu.|  
|[GetState](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|Získá stav Čeká na zarážky.|  
|[GetBreakpointRequest](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|Získá požadavek zarážek použít k vytvoření čekající zarážky.|  
|[Povolit](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|Přepne stav povoleno čekající zarážky.|  
|[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|Vytvoří výčet všech zarážky vázaný z čekající zarážky.|  
|[EnumErrorBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|Zobrazí všechny zarážky chyby, které jsou výsledkem čekající zarážky.|  
|[Odstranit](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|Odstraní čekající zarážek a všechny zarážky vázaný z něj.|  
  
 Výčet vázané zarážky a zarážky chyba, je nutné implementovat všechny metody [IEnumDebugBoundBreakpoints2](../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) a [IEnumDebugErrorBreakpoints2](../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md).  
  
 Čekající na vyřízení zarážky, které vytvořit vazbu na kód umístění vyžadují implementace následující [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|Získá čekající zarážek, který obsahuje zarážku.|  
|[GetState](../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|Získá stav vázané breakpoint.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|Získá zarážek řešení, která popisuje zarážky.|  
|[Povolit](../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|Povolí nebo zakáže zarážky.|  
|[Odstranit](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|Odstraní vázané breakpoint.|  
  
 Překlad IP adres a žádost o informace vyžadují implementace následující [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)|Získá druh breakpoint reprezentována řešení.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)|Získá informace zarážek řešení, které popisují zarážky.|  
  
 Řešení chyb, které mohou nastat během vazby vyžaduje implementaci následující [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)|Získá čekající zarážek, obsahující zarážek k chybě.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)|Získá rozlišení zarážek chyby, které popisuje zarážek k chybě.|  
  
 Řešení chyb, které mohou nastat během vazby taky vyžaduje tyto metody [IDebugErrorBreakpointResolution2](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md).  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)|Získá typ zarážky.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)|Získá informace o řešení v zarážky.|  
  
 Zobrazení zdrojového kódu na zarážce vyžaduje, abyste implementují metody [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) nebo metody [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md).  
  
## <a name="see-also"></a>Viz také  
 [Řízení provádění a vyhodnocení stavu](../../extensibility/debugger/execution-control-and-state-evaluation.md)