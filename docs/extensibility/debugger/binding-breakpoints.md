---
title: "Vazba zarážky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: breakpoints, binding
ms.assetid: 70737387-c52f-4dae-8865-77d4b203bf25
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 55416d6b156055d967424476f5add3b4ed75d18d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="binding-breakpoints"></a>Vazba zarážky
Pokud uživatel nastaví zarážku, možná stisknutím klávesy F9, rozhraní IDE výrobky zpracovává žádost a vyzve k relaci ladění k vytvoření zarážce.  
  
## <a name="setting-a-breakpoint"></a>Nastavení boru přerušení  
 Nastavení boru přerušení je dvoustupňový proces, protože kód nebo data vliv zarážce nemusí být ještě dostupný. Nejprve musí být popsány zarážce a pak Jakmile kód nebo data k dispozici, se musí být vázána na tento kód nebo data, následujícím způsobem:  
  
1.  Je požadován zarážce z motorů relevantní ladění (DEs) a pak zarážce vázána na kód nebo data, jakmile je k dispozici.  
  
2.  Breakpoint – požadavek odeslán do relace ladění, který odesílá, aby všechny relevantní DEs. Všechny DE, který vybere možnost zpracování zarážce vytvoří odpovídající čekající na vyřízení zarážek.  
  
3.  Relaci ladění shromažďuje čekající zarážky a odešle je zpět do balíčku debug (ladění součástí sady Visual Studio).  
  
4.  Ladění balíčku zobrazí výzvu k relaci ladění vytvořit vazbu na vyřízení zarážek kód nebo data. Relaci ladění odešle tento požadavek na všechny relevantní DEs.  
  
5.  Pokud je DE je schopen vytvořit vazbu zarážek, odešle, že zarážku vázána událostí zpět na relaci ladění. Pokud ne, odešle chybová událost zarážek místo.  
  
## <a name="pending-breakpoints"></a>Čekající zarážky  
 Čekající zarážek můžete vázat na víc umístění kódu. Například řádek zdrojového kódu C++ šablony můžete vázat na každý kód pořadí vygenerovaná z této šablony. Relaci ladění můžete použít k vygenerování události vázané Breakpoint – výčet kontexty kód vázána na zarážky v době, kdy byla odeslána událost. Další kód kontexty mohou být vázány později, tak DE mohou odesílat že více zarážek vázaný události pro každý požadavek vazby. Ale Zavedenými by měli poslat jenom jedna událost chyby zarážek každý požadavek vazby.  
  
## <a name="implementation"></a>Implementace  
 Prostřednictvím kódu programu, balíček ladění volá relace ladění správce (SDM) a k němu přiřadí [IDebugBreakpointRequest2](../../extensibility/debugger/reference/idebugbreakpointrequest2.md) rozhraní, které zabaluje [BP_REQUEST_INFO](../../extensibility/debugger/reference/bp-request-info.md) struktura, která popisuje Breakpoint – nastavení. I když zarážky může mít celou řadu forem, budou nakonec odkazující na kód nebo data kontextu.  
  
 SDM předá volání každý relevantní DE voláním jeho [CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) metoda. Pokud je DE vybere možnost zpracování zarážce, vytvoří a vrátí [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) rozhraní. SDM shromažďuje těchto rozhraní a předá je zpět do balíčku ladění jako jeden `IDebugPendingBreakpoint2` rozhraní.  
  
 Pokud byly generovány žádné události.  
  
 Ladění balíček následně se pokusí vytvořit vazbu na vyřízení zarážek kódu nebo dat voláním [vazby](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md), které je implementované DE.  
  
 Pokud je vázána zarážek, DE odešle [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) rozhraní události k ladění balíčku. Použití balíčku ladění toto rozhraní se vytvořit výčet všech kontextů kódu (nebo kontext jednoho datového) vázaný na zarážku voláním [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md), která vrací jednu nebo více [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) rozhraní. [GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md) rozhraní vrátí [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) rozhraní, a [GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) vrátí [BP_ RESOLUTION_INFO](../../extensibility/debugger/reference/bp-resolution-info.md) – typ union obsahující kontext kód nebo data.  
  
 Pokud je DE nelze vytvořit vazbu zarážek, odešle jedné [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) rozhraní události k ladění balíčku. Balíček ladění načte typ chyby (chyby nebo upozornění) a informační zpráva voláním [GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md), za nímž následují [GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) a [ GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md). Tento příkaz vrátí [BP_ERROR_RESOLUTION_INFO](../../extensibility/debugger/reference/bp-error-resolution-info.md) struktura, která obsahuje typ chyby a zprávy.  
  
 Pokud Zavedenými zpracovává zarážku, ale nemůže vytvořit vazbu, vrátí chybu typu `BPET_TYPE_ERROR`. Balíček ladění odpoví tím, že zobrazuje dialogové okno chyby, a rozhraní IDE umístí vykřičníku glyfy uvnitř glyfy zarážek nalevo od řádek zdrojového kódu.  
  
 Pokud Zavedenými zpracovává zarážku, nelze vytvořit vazbu, ale některé jiné DE vázat ji, vrátí upozornění. Prostředí IDE reaguje glyf otázku uvnitř glyfy zarážek nalevo od řádku kódu původního umístění.  
  
## <a name="see-also"></a>Viz také  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)