---
title: "Základní rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], core interfaces
ms.assetid: 666b9116-8550-4bdd-bc15-55fc57de87df
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 54ecbe034f4fa7054be2725205a013e5899849e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="core-interfaces"></a>Základní rozhraní
Následující rozhraní jsou základní rozhraní pro rozšíření ladicí program pomocí [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)].  
  
## <a name="discussion"></a>Diskusní  
 Tato rozhraní se primárně používají vytvořit modul ladění (DE). Jejich uspořádání zde podle kategorií:  
  
-   [Zarážky](#Breakpoints)  
  
-   [Kontexty](#Contexts)  
  
-   [Jádro serveru](#CoreServer)  
  
-   [Ladění moduly](#DebugEngines)  
  
-   [Dokumenty](#Documents)  
  
-   [Události](#Events)  
  
-   [Výrazy](#Expressions)  
  
-   [Paměť](#Memory)  
  
-   [Moduly](#Modules)  
  
-   [Porty](#Ports)  
  
-   [Procesy](#Processes)  
  
-   [Programy](#Programs)  
  
-   [Vlastnosti](#Properties)  
  
-   [Bloky zásobníku](#StackFrames)  
  
-   [Vlákna](#Threads)  
  
-   [Typ Vizualizérech](#TypeVisualizers)  
  
 Entitami, které můžete implementovat rozhraní jsou:  
  
-   Ladění modulu (DE)  
  
-   Port dodavatele (PS)  
  
-   Vyhodnocovací filtr výrazů (EE)  
  
-   Visual Studio (VS)  
  
##  <a name="Breakpoints"></a>Zarážky  
 Tato rozhraní se vztahují k provádění a sledování zarážky.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)|NĚMECKO|Představuje zarážku vázána na umístění paměti.|  
|[IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|NĚMECKO|Odešle DE případě zarážku je vázána na umístění v paměti.|  
|[IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)|sada VS|Představuje kontrolní součet dokumentu pro žádost o zarážek.|  
|[IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|NĚMECKO|Odešle DE případě zarážku nepodaří navázat na umístění paměti.|  
|[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)|NĚMECKO|Poslal DE, když je dosaženo zarážky.|  
|[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)|sada VS|Představuje žádost o zarážku; použité při vytváření čekající zarážky.|  
|[IDebugBreakpointRequest3](../../../extensibility/debugger/reference/idebugbreakpointrequest3.md)|sada VS|Představuje žádost o zarážku; použité při vytváření čekající zarážky.|  
|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|NĚMECKO|Představuje informace, které slouží k vytvoření vazby zarážky.|  
|[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|NĚMECKO|Odesílá DE po zarážku nevázaný z oblasti paměti.|  
|[IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)|NĚMECKO|Představuje neplatný zarážek (vrácený `IDebugBreakpointErrorEvent2`).|  
|[IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)|NĚMECKO|Představuje řešení informace o neplatný bod přerušení.|  
|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|NĚMECKO|Představuje pozici ve funkci, kde je nastavit zarážky.|  
|[IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)|NĚMECKO|Představuje zarážek, který má být vázána; použité při vytváření vázané breakpoint.|  
|[IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)|NĚMECKO|Představuje Výčtový objekt v rámci sady vázané zarážky.|  
|[IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)|NĚMECKO|Představuje Výčtový objekt v rámci sady zarážky, které nebylo možné svázat do umístění v paměti.|  
  
##  <a name="Contexts"></a>Kontexty  
 Tato rozhraní představují různé druhy kontexty v rámci programu laděné.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|NĚMECKO|Představuje počáteční pozici instrukce kódu.|  
|[IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)|NĚMECKO|Rozšiřuje [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní, abyste umožnili načtení modulu a proces rozhraní.|  
|[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)|VS, DE|Představuje pozici v dokumentu.|  
|[IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)|NĚMECKO|Představuje kontext, ve kterém má být výraz.|  
|[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)|NĚMECKO|Představuje výchozí umístění v paměti kolekce bajtů.|  
|[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)|NĚMECKO|Představuje kontext rámce zásobníku v zarážek nebo výjimky.|  
|[IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)|NĚMECKO|Představuje kontext rámce zásobníku v zarážek nebo výjimky.|  
|[IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)|NĚMECKO|Představuje Výčtový objekt v rámci sady kontexty kódu.|  
  
##  <a name="CoreServer"></a>Jádro serveru  
 Tato rozhraní představuje počítač, na kterém je ladit program. Tyto jsou implementované [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] , ale může být volána do ladění moduly.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)|sada VS|Poskytuje přístup k porty a dodavatelé port a také informace o počítači.|  
|[IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)|sada VS|Představuje [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) podporuje vzdálené ladění.|  
  
##  <a name="DebugEngines"></a>Ladění moduly  
 Tato rozhraní představují moduly ladění a jejich přidružené události.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)|NĚMECKO|Představuje modul vlastní ladění.|  
|[IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)|NĚMECKO|Představuje modul vlastní ladění, který podporuje načítání symboly, JustMyCode a výjimky.|  
|[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)|NĚMECKO|Odešle každou novou instanci třídy DE znamenat, že je připraven k zpracování úkolů ladění.|  
|[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)|NĚMECKO|Představuje modul vlastní ladění, který podporuje spuštění programy.|  
|[IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)|NĚMECKO, PS|Představuje uzel program, který zpracovává více modulů ladění.|  
|[IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)|NĚMECKO|Poskytuje způsob, jak SDM získat rozhraní k modulu ladění z vlákna, programu nebo rámce zásobníku.|  
  
##  <a name="Documents"></a>Dokumenty  
 Tato rozhraní představují dokumenty (zdrojové soubory) a jejich přidružených elementů.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|NĚMECKO|Odešle DE požádat o otevření dokumentu.|  
|[IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)|NĚMECKO|Představuje datový proud bylo pokyny z dokumentu.|  
|[IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)|VS, DE|Reprezentuje dokument poskytl DE, zadáte název a třídu ID (CLSID).|  
|[IDebugDocumentChecksum2](../../../extensibility/debugger/reference/idebugdocumentchecksum2.md)|NĚMECKO, EE|Představuje kontrolního součtu pro dokument ladění a umožňuje předávání kontrolního součtu mezi součástmi.|  
|[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)|VS, DE|Představuje kontext dokumentu, na pozici v rámci dokumentu odpovídající konkrétní příkaz a kód kontextu.|  
|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|VS, DE|Představuje obecné pozici v rámci dokumentu.|  
|[IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)|sada VS|Představuje pozici ve zdrojovém souboru jako odsazení znaku.|  
|[IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)|VS, DE|Představuje textový dokument poskytl DE (odvozený z [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)), poskytuje vlastní text.|  
|[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|NĚMECKO|Odešle DE zadejte změny zdrojový soubor, který je v paměti.|  
  
##  <a name="Events"></a>Události  
 Tato rozhraní představují všechny události, které se odesílají mezi DE a správce ladicí relace (SDM).  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|NĚMECKO|Odešle DE požádat o otevření dokumentu.|  
|[IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md)|NĚMECKO|Modul ladění (DE) odešle toto rozhraní správce ladicí relace (SDM) Chcete-li nastavit stav panelu zpráv během načítání symbol.|  
|[IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)|NĚMECKO|Odesílá DE po dokončení zalomení v programu.|  
|[IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|NĚMECKO|Odešle DE v případě, že je vázán zarážky.|  
|[IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|NĚMECKO|Odešle DE případě zarážku nepodaří navázat.|  
|[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)|NĚMECKO|Poslal DE, když je dosaženo zarážky.|  
|[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|NĚMECKO|Odesílá DE po nevázaný zarážky.|  
|[IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)|NĚMECKO|Odesílá DE k určení, jestli by se měla zastavit v konkrétních místech.|  
|[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|NĚMECKO|Odešle DE zadejte změny zdrojový soubor, který je v paměti.|  
|[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)|NĚMECKO|Odešle každou novou instanci třídy DE znamenat, že je připraven k zpracování úkolů ladění.|  
|[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)|NĚMECKO|Odešle DE znamenat, že program laděné je připraven provést první instrukcí.|  
|[IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)|NĚMECKO|Rozhraní, které se používá rozhraní dalších událostí, které může způsobit chybu, k zajištění čitelná pro člověka chybové zprávy.|  
|[IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)|NĚMECKO, PS|Základní rozhraní, ze které všechny události jsou odvozeny rozhraní.|  
|[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)|sada VS|Představuje rozhraní implementované SDM, ke které se odesílají události (vyjádřeno jako objekty implementace rozhraní určitá událost).|  
|[IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)|NĚMECKO|Odešle DE v případě, že v programu laděné došlo k výjimce.|  
|[IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|NĚMECKO|Odesílá DE po dokončení asynchronní výraz zkušební verzi.|  
|IDebugFindSymbolEvent2||ZASTARALÉ. NEPOUŽÍVEJTE.|  
|[IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)|NĚMECKO|Odesílá DE po dokončení zpracování pro zachycené výjimku.|  
|[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)|NĚMECKO|Odesílá DE program po dokončení načítání.|  
|[IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)|NĚMECKO|Poslal DE tak, aby měl zobrazení IDE informační zpráva uživateli.|  
|[IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|NĚMECKO|Odesílá DE při načtení nebo odpojení modulu.|  
|[IDebugNoSymbolsEvent2](../../../extensibility/debugger/reference/idebugnosymbolsevent2.md)|NĚMECKO|Signály [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladicího programu uživatelského rozhraní uživatele upozornit, že symboly nebyl nalezen pro spuštěného spustitelný soubor.|  
|[IDebugOutputStringEvent2](../../../extensibility/debugger/reference/idebugoutputstringevent2.md)|NĚMECKO|Odesílá DE tak, aby měl zobrazení IDE libovolný řetězec.|  
|[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)|VS, DE|Odesílá port pro komunikaci portu události pro všechny naslouchací proces.|  
|[IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)|NĚMECKO, PS|Odesílají DE nebo portu po vytvoření procesu.|  
|[IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)|NĚMECKO, PS|Odešle DE nebo port v případě, že proces byl zničen.|  
|[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|NĚMECKO, PS|Odesílají DE nebo portu po vytvoření programu.|  
|[IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|NĚMECKO, PS|Odešle DE nebo port v případě, že program byl zničen.|  
|[IDebugProgramDestroyEventFlags2](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2.md)|NĚMECKO|Umožňuje přepsat výchozí chování stroj ladění [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní při ukončení relace ladění.|  
|[IDebugProgramNameChangedEvent2](../../../extensibility/debugger/reference/idebugprogramnamechangedevent2.md)|NĚMECKO|Odeslaný modul ladění (DE) zadaný pro relaci ladění správce (SDM) při změně název programu.|  
|[IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|NĚMECKO|Poslal DE při novou vlastnost (reprezentována `IDebugProperty2` rozhraní) byla vytvořena.|  
|[IDebugPropertyDestroyEvent2](../../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|NĚMECKO|Odešle DE případě vlastnost byl zničen.|  
|[IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)|NĚMECKO|Odešle DE případě krokování s vynořením nebo přes funkci, návratová hodnota může být správně zobrazen.|  
|[IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)|sada VS|Umožňuje ladění moduly číst nastavení metriky vzdáleně.|  
|[IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)|NĚMECKO|Po dokončení kroku do, přes nebo mimo instrukce poslal DE.|  
|[IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)|NĚMECKO|Odesílá DE indikující úspěch nebo selhání načtení symbolů pro modul.|  
|[IDebugThreadCreateEvent2](../../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|NĚMECKO|Odesílá DE po vytvoření vlákna.|  
|[IDebugThreadDestroyEvent2](../../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|NĚMECKO|Odešle DE případě vlákno byl zničen.|  
|[IDebugThreadNameChangedEvent2](../../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|NĚMECKO|Odešle DE případě vlákna došlo ke změně jeho názvu.|  
  
##  <a name="Expressions"></a>Výrazy  
 Tato rozhraní představují výrazy, který se má vyhodnotit pro konkrétní účely.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)|NĚMECKO|Představuje výraz, který se vyhodnotí. Získaný [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní.|  
|[IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)|NĚMECKO|Představuje kontext, ve které je výraz vyhodnocen. Získaný [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní.|  
|[IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|NĚMECKO|Odesílá DE po dokončení asynchronní výraz zkušební verzi.|  
  
##  <a name="Memory"></a>Paměť  
 Tato rozhraní představují pořadí bajtů v paměti.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)|NĚMECKO|Představuje sekvenci bajtů v paměti, který může číst nebo zapisovat do.|  
|[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)|NĚMECKO|Představuje umístění v paměti pořadí bajtů.|  
  
##  <a name="Modules"></a>Moduly  
 Tato rozhraní představují modul, který odpovídá spustitelný soubor nebo. Soubor DLL.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)|NĚMECKO|Představuje jeden spustitelný soubor nebo DLL.|  
|[IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)|NĚMECKO|Představuje [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) podporující symboly.|  
|[IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|NĚMECKO|Odesílá DE při načtení nebo odpojení modulu.|  
|[IDebugSourceServerModule](../../../extensibility/debugger/reference/idebugsourceservermodule.md)|NĚMECKO|Představuje informace o zdrojovém serveru, obsažené v souboru PDB.|  
|[IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)|NĚMECKO|Představuje Výčtový objekt v rámci sady modulů, které jsou známé podle [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md).|  
  
##  <a name="Ports"></a>Porty  
 Tato rozhraní představují porty a všichni dodavatelé portu.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)|VS, PS|Představuje výchozí port v místním počítači.|  
|[IDebugFirewallConfigurationCallback2](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2.md)|sada VS|Povolí ladění modul, který používá model DCOM a požádejte [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní a ujistěte se, že brána firewall neblokuje vzdálené ladění.|  
|[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)|VS, PS|Reprezentuje port.|  
|[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)|PS|Odesílá port pro komunikaci portu události pro všechny naslouchací proces.|  
|[IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)|PS|Představuje na port, který můžete spustit a ukončit procesy.|  
|[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)|PS|Používá k registraci a zrušit registraci programy s portem; umožňuje sledovat programy právě laděn port.|  
|[IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)|PS|Představuje vlastní uživatelské rozhraní pro výběr port.|  
|[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)|sada VS|Představuje žádost o portu, ze kterého se vytvoří nový port nebo nachází.|  
|[IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)|PS|Představuje dodavatele portů.|  
|[IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)|PS|Představuje dodavatele porty, které můžete zachovat (Uložit na disk) informace o portech ji vytvořit.|  
|[IDebugPortSupplierDescription2](../../../extensibility/debugger/reference/idebugportsupplierdescription2.md)|PS|Umožňuje [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní k zobrazení textu uvnitř **přenosu informací** části **připojit k procesu** dialogové okno.|  
|[IDebugWindowsComputerPort2](../../../extensibility/debugger/reference/idebugwindowscomputerport2.md)|sada VS|Umožňuje dotazování na informace o cílovém počítači.|  
|[IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)|VS, PS|Představuje výčet přes sadu portů.|  
|[IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)|sada VS|Představuje Výčtový objekt v rámci sady dodavatelé portu.|  
  
##  <a name="Processes"></a>Procesy  
 Tato rozhraní představují procesy, jeden spustitelný soubor, který obsahuje jeden nebo více programů.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)|PS, DE|Představuje proces, který běží na počítači.|  
|[IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)|PS, DE|Představuje proces, který podporuje aktivně ladění (používá k nahrazení krokem, pokračovat a spustit metody na [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní).|  
|[IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)|NĚMECKO, PS|Odesílají DE nebo portu po vytvoření procesu.|  
|[IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)|NĚMECKO, PS|Odešle DE nebo port v případě, že proces byl zničen.|  
|[IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)|PS|Představuje proces, který musí sledování relace, který je připojen k němu.|  
|[IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)|PS|Představuje výčet sady procesů na portu.|  
  
##  <a name="Programs"></a>Programy  
 Tato rozhraní představují programy, provádění logických jednotkách, které neodpovídají nutně fyzické spustitelný soubor nebo modul.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)|NĚMECKO|Představuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) potřebného pro práci ve vzájemné součinnosti s jinými programy laděné ve stejnou dobu.|  
|[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)|NĚMECKO, PS|Představuje logickou jednotkou spouštění.|  
|[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|NĚMECKO, PS|Odesílají DE nebo portu po vytvoření programu.|  
|[IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|NĚMECKO, PS|Odešle DE nebo port v případě, že program byl zničen.|  
|[IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)|NĚMECKO, PS|Představuje [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) , můžete ji zpracovat více modulů ladění.|  
|[IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)|PS|Představuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) , musí být schopný sledovat, které relace je připojen k němu.|  
|[IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)|NĚMECKO, PS|Představuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) , může vrátit informace o procesu, ve kterém je spuštěna.|  
|[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)|NĚMECKO, PS|Představuje program, který můžete ladit.|  
|[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)|NĚMECKO, PS|Umožňuje programu uzlu upozornit pokus o připojení k programu přidružené.|  
|[IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)|NĚMECKO|Poskytuje způsob, jak SDM dotazovat DE o programy, které řídí že DE.|  
|[IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)|sada VS|Při registraci programy s SDM zobrazit, že se právě ladí používá šifrování DEs.|  
|[IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)|NĚMECKO, PS|Představuje [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní, můžete zařazování hranice podprocesu nebo proces.|  
|[IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)|NĚMECKO, PS|Představuje výčet sady programů.|  
  
##  <a name="Properties"></a>Vlastnosti  
 Tato rozhraní představují vlastnosti přidružené k určitému kontextu, obvykle výsledkem vyhodnocení výrazu hodnotu.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)|EE|Představuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) vlastním způsobem, který můžete zobrazit jeho hodnotu.|  
|[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)|NĚMECKO|Reprezentuje hodnotu rámce zásobníku, dokumentu nebo výsledkem vyhodnocení výrazu.|  
|[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)|NĚMECKO|Představuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) dlouhé řetězce, který podporuje.|  
|[IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|NĚMECKO|Poslal DE při novou vlastnost (reprezentována [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní) byla vytvořena.|  
|[IDebugPropertyDestroyEvent2](../../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|NĚMECKO|Odešle DE případě vlastnost byl zničen.|  
|[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)|NĚMECKO|Představuje odkaz na vlastnost, která může existovat mimo rámec žádné konkrétní zásobníku.|  
|[IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)|NĚMECKO|Představuje výčet přes sadu [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury, které popisují proměnné, registry, parametry a výrazy.|  
|[IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)|NĚMECKO|Představuje výčet přes sadu [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury.|  
  
##  <a name="StackFrames"></a>Rámce zásobníku  
 Tato rozhraní představují rámce zásobníku, kontextu v které zarážek nebo výjimky došlo k chybě.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)|NĚMECKO|Představuje kontext ve které zarážek nebo výjimky došlo k chybě.|  
|[IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)|NĚMECKO|Představuje [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) která dokáže zpracovat zachycení výjimky.|  
|[IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)|NĚMECKO|Představuje výčet přes sadu [CODE_PATH](../../../extensibility/debugger/reference/code-path.md) sekvence použité k získání konkrétní zásobníku volání struktury, které určují funkce.|  
|[IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)|NĚMECKO|Představuje výčet přes sadu [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury, které popisují rámce zásobníku.|  
  
##  <a name="Threads"></a>Vláken  
 Tato rozhraní představují vláken a jejich přidružené události.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|NĚMECKO|Představuje podproces provádění.|  
|[IDebugThreadCreateEvent2](../../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|NĚMECKO|Odesílá DE po vytvoření vlákna.|  
|[IDebugThreadDestroyEvent2](../../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|NĚMECKO|Odešle DE případě vlákno byl zničen.|  
|[IDebugThreadNameChangedEvent2](../../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|NĚMECKO|Odešle DE případě vlákna došlo ke změně jeho názvu.|  
|[IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)|NĚMECKO|Představuje Výčtový objekt v rámci sady vláken.|  
  
##  <a name="TypeVisualizers"></a>Typ Vizualizérech  
 Tato rozhraní poskytují podporu pro typ vizualizérech. Tato rozhraní jsou obvykle implementované vyhodnocovací filtr výrazů.  
  
|Rozhraní|Implementované|Popis|  
|---------------|--------------------|-----------------|  
|[IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)|EE|Představuje pole bajtů, které mají být předány vizualizéru typ.|  
|[IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)|EE|Poskytuje metody pro získání přístupu k datům, které mají být předány vizualizéru typu.|  
|[IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)|EE|Reprezentuje vlastnost, která poskytuje přístup k [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) implementace.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace rozhraní API](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)   
 [Vytvoření vlastního ladicího stroje](../../../extensibility/debugger/creating-a-custom-debug-engine.md)