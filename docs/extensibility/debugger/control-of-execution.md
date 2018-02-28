---
title: "Řízení provádění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 97071846-007e-450f-95a6-f072d0f5e61e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a76b14f28bdb74345813931fc334f98090abd93c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="control-of-execution"></a>Řízení spouštění
Modul ladění (DE) obvykle odešle jednu z následujících událostí jako poslední událost spuštění:  
  
-   Položka bodu událost, pokud se připojuje k nově spuštěného programu  
  
-   Událost complete zatížení, pokud se připojuje k programu, který je již spuštěna  
  
 Obě tyto události jsou zastavování události, což znamená, že je DE čeká na odpověď od uživatele prostřednictvím rozhraní IDE. Další informace najdete v tématu [provozní režimy](../../extensibility/debugger/operational-modes.md).  
  
## <a name="stopping-event"></a>Zastavení událostí  
 Při zastavení událostí posílá relaci ladění:  
  
1.  Program a vlákno, které obsahují aktuální ukazatel instrukce je možné získat z rozhraní událostí.  
  
2.  Prostředí IDE Určuje aktuální souboru zdrojového kódu a pozice, který se zobrazí zvýrazněných v editoru.  
  
3.  Relaci ladění se obvykle odpovídá na tento první událost zastavení voláním programu **pokračovat** metoda.  
  
4.  Program se pak spustí, dokud zjistí zastavení podmínky, například stiskne zarážku, ve kterém případ DE odešle zarážek událostí na relaci ladění. Událost zarážek je událost zastavení a DE znovu čeká na odpověď uživatele.  
  
5.  Pokud se uživatel rozhodne za krok do, nebo mimo funkci rozhraní IDE zobrazí výzvu relaci ladění volat program `Step` metoda, předání jednotky krok (instrukce, příkaz nebo řádek) a typ kroku – to znamená, jestli se má krok do, více než , nebo mimo funkci. Po dokončení kroku DE odešle událost complete krok relaci ladění, které je událost zastavit.  
  
     -nebo-  
  
     Pokud se uživatel rozhodne pokračovat v provádění z aktuální ukazatel instrukce, rozhraní IDE zobrazí výzvu k relaci ladění volat program **Execute** metoda. Program obnoví spuštění, dokud zjistí další podmínky zastavit.  
  
     -nebo-  
  
     Pokud relaci ladění bude ignorovat konkrétní zastavení událostí, zavolá relaci ladění programu **pokračovat** metoda. Pokud program byl krokování do, přes nebo mimo funkci byla zjištěna podmínku zastavit, potom pokračuje v kroku.  
  
 Prostřednictvím kódu programu, když je DE zjistí stav, zastavení, odešle tyto události zastavení jako [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) nebo [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) pro relaci ladění správce (SDM) prostřednictvím [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) rozhraní. DE předává [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) a [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) rozhraní, které představují program a vlákno obsahující aktuální ukazatel instrukce. Volání SDM [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) nejvyšší zásobníku a volání [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) získat dokument kontext přidružený aktuální instrukcí ukazatel. Kontextu tohoto dokumentu je obvykle zdrojovém kódu souboru název, čísla řádků a sloupců. Rozhraní IDE používá tyto zvýrazněte zdrojový kód, který obsahuje aktuální ukazatel instrukce.  
  
 SDM obvykle odpovídá na tento první událost zastavení voláním [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md). Poté spustí program dokud zjistí zastavení podmínky, například stiskne zarážku, ve kterém případ DE odešle [IDebugBreakpointEvent2 rozhraní](../../extensibility/debugger/reference/idebugbreakpointevent2.md) k SDM. Událost zarážek je událost zastavení a DE znovu čeká na odpověď uživatele.  
  
 Pokud se uživatel rozhodne za krok do, nebo mimo funkci rozhraní IDE zobrazí výzvu SDM volat [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md), předání [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) (instrukce, příkaz nebo řádek) a [ STEPKIND](../../extensibility/debugger/reference/stepkind.md), to znamená, jestli se má krok do, přes nebo mimo funkci. Po dokončení kroku DE odešle [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) rozhraní SDM, které je událost zastavit.  
  
 Pokud se uživatel rozhodne pokračovat v provádění z aktuální ukazatel instrukce, rozhraní IDE zobrazí SDM volat [IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md). Program obnoví spuštění, dokud zjistí další podmínky zastavit.  
  
 Pokud balíček ladění ignorovat konkrétní zastavení událostí, volá ladění balíček SDM, který volá [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md). Pokud program byl krokování do, přes nebo mimo funkci byla zjištěna podmínku zastavit, potom pokračuje v kroku. Z toho vyplývá, že program udržuje taktování stavu, tak, aby věděl, že může jak pokračovat.  
  
 Volání SDM provede `Step`, **Execute**, a **pokračovat** jsou asynchronní, což znamená, že SDM očekává, že volání rychle vrátit. Pokud je DE odešle SDM zastavení událostí ve stejném vlákně, před `Step`, **Execute**, nebo **pokračovat** vrátí SDM přestane reagovat.  
  
## <a name="see-also"></a>Viz také  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)