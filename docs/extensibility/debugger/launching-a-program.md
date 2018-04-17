---
title: Spuštění programu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- programs, launching
ms.assetid: 6857e9c6-e44a-468a-afa4-f7c4a0b77844
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 714d751e9855b5567bf76ccd902fada727e14ba1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="launching-a-program"></a>Spuštění programu
Uživatelé, kteří chtějí k ladění programu můžete stisknutím klávesy F5 spusťte ladicí program z prostředí IDE. To začne řadu událostí, které konečným výsledkem je rozhraní IDE připojení k modul ladění (DE), který je pak připojení nebo připojení k programu následujícím způsobem:  
  
1.  Prostředí IDE nejprve zahájí volání balíčku projektu získat aktivní projekt řešení nastavení pro ladění. Nastavení zahrnuje spouštěcí adresář, proměnné prostředí, port, ve kterém se bude program spouštět a DE sloužící k vytvoření programu, pokud zadaný. Tato nastavení se předávají do balíčku ladění.  
  
2.  Pokud je zadán Zavedenými, DE volá operačního systému spustit program. V důsledku spuštění programu, je načten program běhové prostředí. Například pokud program je napsána v MSIL, modul CLR bude volána pro spuštění programu.  
  
     -nebo-  
  
     Pokud není zadán Zavedenými, zavolá port operačního systému na spuštění programu, což způsobí, že program běhové prostředí má být načten.  
  
    > [!NOTE]
    >  Pokud Zavedenými slouží ke spuštění programu, je pravděpodobné, že stejné DE bude připojen k programu.  
  
3.  V závislosti na tom, jestli je DE nebo port spuštění programu DE nebo běhové prostředí poté vytvoří popis programu, nebo uzel a upozorní portu, na kterém je aplikace spuštěna.  
  
    > [!NOTE]
    >  Doporučujeme, běhové prostředí vytvořit program uzlu, protože uzel programu je lightweight reprezentace program, který můžete ladit. Není nutné načíst nahoru celé DE jenom k vytvořit a registrovat program uzlu. Pokud je DE slouží ke spuštění procesu prostředí IDE, ale žádné IDE je ve skutečnosti spuštěna, je potřeba komponenty, která můžete přidat uzel, program na port.  
  
 Nově vytvořený programu, společně s všechny ostatní programy související nebo nesouvisející, spuštění nebo připojené k ze stejné IDE, napište na relaci ladění.  
  
 Prostřednictvím kódu programu, když uživatel nejprve stiskne **F5**, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]na balíček ladění zahájí volání balíčku projektu (jenž je spojený s typem spuštění programu) prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> metodu, která pak vyplňuje <xref:Microsoft.VisualStudio.Shell.Interop.VsDebugTargetInfo2> struktura s nastavením pro ladění na řešení aktivního projektu. Tato struktura je předán zpět do balíčku ladění prostřednictvím volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger2.LaunchDebugTargets2%2A> metoda. Ladění balíček pak vytvoří správce ladicí relace (SDM), který spouští programu, který je ladění vyladěnou a všechny přidružené moduly.  
  
 Jeden z argumentů předaný SDM je identifikátor GUID DE, který se má použít ke spuštění programu.  
  
 Pokud není identifikátor GUID DE `GUID_NULL`, SDM společně vytvoří DE a potom zavolá jeho [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) metoda ke spuštění programu. Například, pokud program je zapsán v nativním kódu, pak `IDebugEngineLaunch2::LaunchSuspended` pravděpodobně zavolá `CreateProcess` a `ResumeThread` (Win32 funkce) ke spuštění programu.  
  
 V důsledku spuštění programu, je načten program běhové prostředí. DE nebo běhové prostředí poté vytvoří [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní pro popis programu a předá tohoto rozhraní [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) oznámit port, který je program spuštěna.  
  
 Pokud `GUID_NULL` je předán, pak port spouští program. Jakmile program běží, vytvoří běhové prostředí `IDebugProgramNode2` rozhraní pro popis programu a předává jej do `IDebugPortNotify2::AddProgramNode`. To upozorní portu, na kterém je aplikace spuštěna. Potom SDM připojí modul ladění spuštěného programu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Upozornění portu](../../extensibility/debugger/notifying-the-port.md)  
 Vysvětluje, co se stane po spuštění programu a port je upozornění.  
  
 [Připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md)  
 Dokumenty při relaci ladění je připraven k DE připojit k programu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé ladění úlohy, jako je například spuštěním programu a vyhodnocení výrazů.