---
title: Spuštění ladicí relace pro aplikace pro UPW v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCAppHostRemoteDebugPageObject.MachineName
- VC.Project.IVCAppHostRemoteDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostTetheredDebugPageObject.DebuggerType
- VC.Project.IVCAppHostLocalDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostRemoteDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.DebuggerType
- ImmersiveProjects.Properties.Debug
- VC.Project.IVCAppHostTetheredDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostLocalDebugPageObject.AllowLocalNetworkLoopback
- AppPackage.Properties.Debug
- VC.Project.IVCAppHostRemoteDebugPageObject.Authentication
- VC.Project.IVCAppHostRemoteDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.BreakpointBehavior
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: a7a9f74450ccf2cb493e44fa1fecef0630a27569
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49818781"
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio"></a>Spuštění ladicí relace pro aplikace pro UPW v sadě Visual Studio
  
 Toto téma popisuje způsob spuštění ladicí relace pro aplikace pro UPW v XAML a Visual C++, Visual C#, nebo Visual Basic a pro aplikace pro UPW napsané v HTML a JavaScript. Ladění aplikace zahrnuje konfiguraci relace ladění i volba způsob, jak spustit aplikaci.  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a> Snadný způsob, jak spustit ladění  
  
1. Otevřete aplikaci řešení v sadě Visual Studio.  
  
2. Vyberte tlačítko F5.  
  
   Visual Studio vytvoří a spustí aplikaci s připojeným ladícím nástrojem. Provádění pokračuje, dokud není dosaženo zarážky, můžete ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
##  <a name="BKMK_Choose_the_build_configuration_options"></a> Vybrat možnosti konfigurace sestavení  
  
1.   Z rozevíracího seznamu vedle položky **spustit ladění** tlačítko na ladicí program **standardní** nástrojů, zvolte **ladění**.  
  
2.  Z **platformy** seznamu zvolte cílovou platformu pro vytváření pro.  
  
##  <a name="BKMK_Choose_the_deployment_target"></a> Zvolte cíl nasazení  
  
Můžete nasadit a ladit aplikaci UPW na počítač s Visual Studio, připojených zařízení, simulátoru sady Visual Studio na místním počítači, vzdálené zařízení nebo emulátoru. Vyberte cíl nasazení z rozevíracího seznamu vedle **platformy** cílové ladicí program **standardní** nástrojů.
  
![Vyberte cíl nasazení](../debugger/media/vsrun_select_target_device.png)  
  
Vyberte jednu z těchto možností:  
  
|||  
|-|-|  
|**Místní počítač**|Ladění aplikace v aktuální relaci na místním počítači.|  
|**Simulátor**|Ladění aplikace v simulátoru sady Visual Studio pro aplikace pro UPW. Simulátor není okno klasické pracovní plochy, která umožňuje ladit funkce zařízení, například gesta dotykového ovládání a otočení obrazovky –, který nemusí být k dispozici v místním počítači. Tato možnost je k dispozici, pouze pokud vaše aplikace **Min cílové platformy. Verze** je menší než nebo rovna operačního systému na vývojovém počítači. Zobrazit [aplikace spustit UWP v simulátoru](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Vzdálený počítač**|Ladění aplikací na zařízení, který je připojený k místním počítači v síti intranet nebo přímo pomocí kabelu Ethernet. Pro vzdálené ladění, Remote Tools for Visual Studio musí být nainstalovaná a spuštěná na vzdáleném zařízení. Zobrazit [aplikací pro UWP spuštění na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
|**zařízení**|Ladění aplikací na zařízení připojená přes USB. Zařízení musí být odemčené pro vývojáře a odemknutí obrazovky.|  
|**Mobilní emulátor**|Spuštění emulátoru s konfigurací, zadaný v názvu emulátor, nasaďte aplikaci a spusťte ladění. Emulátory jsou dostupné jenom pro počítače Hyper-V povolena.|  

##  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a> Vyberte další možnosti ladění  

Pokud je potřeba nakonfigurovat další možnosti ladění, otevřete jeho stránku vlastností projektu.
  
1.  V Průzkumníku řešení vyberte projekt. V místní nabídce zvolte **vlastnosti**.  
  
2.  Proveďte to k otevření stránky vlastnosti ladění pro projekt:  
  
    -   Pro aplikace Visual C# a Visual Basic, zvolte **ladění**.  
  
         ![C&#35; &#47; stránky vlastnosti ladění projektu jazyka Visual Basic](../debugger/media/dbg_csvb_debugpropertypage.png)  
  
    -   Pro aplikace Visual C++ a JavaScript, rozbalte **vlastnosti konfigurace** uzlu a pak zvolte **ladění**.  
  
         ![C&#43; &#43; stránky vlastnosti ladění aplikace pro UPW](../debugger/media/dbg_cpp_debugpropertypage.png)  

###  <a name="BKMK_Choose_the_debugger_to_use"></a> Zvolte možnost použít ladicí program  
Ve výchozím nastavení Visual Studio ladí spravovaného kódu v aplikacích jazyka C# a Visual Basic. Pro aplikace C# a Visual Basic můžete ladit jak spravovaný a nativní kód C/C++ v aplikaci. V aplikacích jazyka C++ Visual Studio ladí nativního kódu ve výchozím nastavení. V aplikacích jazyka JavaScript sady Visual Studio ladí skript ve výchozím nastavení. 
  
Pro aplikace v C++ a JavaScript můžete ladit konkrétní typy kódu, které jsou součástí vaší aplikace, místo nebo kromě nativní kód. Zadejte kód pro ladění ve **typ ladicího programu** seznamu **ladění** stránku vlastností projektu aplikace.  
  
Vyberte jednu z těchto ladicí programy z **proces aplikace** seznamu:  
  
|||  
|-|-|  
|**Režim pouze spravovaný**|Ladit spravovaný kód ve vaší aplikaci. Kód jazyka JavaScript a nativního kódu C/C++ jsou ignorovány.|  
|**Pouze nativní**|Ladění nativního kódu C/C++ v aplikaci. Spravovaný kód a kód jazyka JavaScript jsou ignorovány.|  
|**Smíšený (spravovaný a nativní)**|Ladění nativního kódu C/C++ a spravovaném kódu ve vaší aplikaci. Kód jazyka JavaScript se ignoruje. V projektech C++, je tato možnost volat **(spravovaný a nativní)**.|  
|**Jenom skript**|Ladění kódu JavaScript ve vaší aplikaci. Nativní a spravovaný kód jsou ignorovány.|  
|**Skript a nativní**|Ladění nativního kódu C/C++ a jazyka JavaScript v aplikaci. Spravovaný kód se ignoruje. K dispozici v pouze projekty C++.|  
|**Jenom grafický procesor (C++ AMP)**|Ladění nativního kódu C++, na které poběží grafický procesor (GPU). K dispozici v pouze projekty C++.|  

V C# a aplikace Visual Basic, můžete také nastavit stejný **typ ladicího programu** hodnoty pro všechny úlohy na pozadí, které jsou součástí projektu.
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a> (Volitelné) Prodleva spuštění relace ladění  
 Ve výchozím nastavení spustí aplikace Visual Studio okamžitě aplikace při spuštění ladění. Můžete také spustit relaci ladění, ale zpoždění spuštění vaší aplikace. Když vyberete tuto možnost, spuštění aplikace v ladicím programu při jeho spuštění na obrazovce Start nebo kliknutím kontrakt aktivace nebo při spuštění jiným procesem nebo metody. Také zpozdíte spuštění vaší aplikace, pokud chcete ladit úlohu na pozadí, když se aplikace.  
  
 Chcete-li zpoždění spuštění vaší aplikace, můžete:  
  
-   Pro aplikace Visual C# a Visual Basic, vyberte **nespouštět, ale ladit můj kód při spuštění** na **ladění** stránku vlastností.  
  
-   Aplikace Visual C++ a JavaScript, zvolte **ne** z **spustit aplikaci** seznamu **ladění** stránku vlastností.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a> (Volitelné) Zakázat vytváření zpětných sítě smyček  
  
 Z bezpečnostních důvodů není povoleno volat síťových zařízení, ve kterých je nainstalované aplikace pro UPW, který je nainstalován standardním způsobem. Ve výchozím nastavení nasazení sady Visual Studio vytvoří výjimku z tohoto pravidla pro aplikace nasazené. Tato výjimka umožňuje testovat postupy komunikace na jednom počítači. Před odesláním aplikace do Microsoft Store, měli byste otestovat vaši aplikaci bez výjimky.  
  
 Chcete-li odebrat výjimku zpětnou smyčku sítě:  
  
-   Pro vizuál C# a aplikací Visual Basic, zrušte **povolit zpětnou smyčku místní sítě** zaškrtávací políčko na **ladění** stránku vlastností.  
  
-   Aplikace Visual C++ a JavaScript, zvolte **ne** z **povolit zpětnou smyčku místní sítě** seznamu **ladění** stránku vlastností.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a> (Volitelné) Nainstalujte aplikaci znovu při spuštění ladění  
 K diagnostice problémů s instalací a počáteční konfiguraci aplikace Visual C# nebo Visual Basic, zvolte **odinstalovat a pak přeinstalovat Můj balíček** na **ladění** znovu vytvořit na stránce vlastností původní instalace při zahájení ladění. Tato možnost není k dispozici pro projekty Visual C++ a JavaScript.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a> (Volitelné) Zakázat ověřování požadavek na spuštění vzdáleného ladicího programu  
  
 Ve výchozím nastavení, musíte zadat přihlašovací údaje spustit vzdálený ladicí program, když vyberete **vzdálený počítač** jako cíl nasazení.
  
> [!IMPORTANT]
>  Můžete také spustit vzdálený ladicí program bez ověřování, ale tento režim se rozhodně nedoporučuje. Při spuštění v tomto režimu není žádné zabezpečení sítě. Vyberte bez ověřování jenom v případě, že jste si jisti, že síť není riziko zneužití škodlivým kódem nebo nebezpečný provoz.  
  
 Chcete-li odebrat požadavek na ověření:  
  
1.  Pro vizuál C# a Visual Basic aplikací, vyberte **vzdálený počítač** jako **cílové zařízení** na **ladění** stránku vlastností a pak nastavte **ověřování Režim** k **žádný** nebo **univerzální (nešifrovaný protokol)**.
  
2.  U aplikací Visual C++ a JavaScript, vyberte **vzdálený počítač** jako **cílové zařízení** na **ladění** stránku vlastností a pak nastavte **vyžadují Ověřování** k **žádný** nebo **univerzální (nešifrovaný protokol)**.  

    **Univerzální (nešifrovaný protokol)** je určen pro použití při nasazování na vzdáleném zařízení. V současné době je to pro zařízení IoT, Xbox zařízení a zařízení HoloLens, jakož i Creators Update nebo novější počítače. Univerzální (nešifrovaný protokol) by měla sloužit pouze v důvěryhodných sítích. Připojení ladění je ohrožené kyberzločinci, kteří by mohl zachytit a změnit dat předávaných mezi vývojem a vzdálený počítač.  
  
##  <a name="BKMK_Start_the_debugging_session"></a> Spuštění ladicí relace  
  
###  <a name="BKMK_Start_debugging__F5_"></a> Spustit ladění (F5)  
 Pokud zvolíte **spustit ladění** (klávesnice: F5) na **ladění** nabídce sady Visual Studio spustí aplikaci s připojeným ladícím nástrojem. Provádění pokračuje, dokud není dosaženo zarážky, můžete ručně pozastavení provádění, dojde k výjimce nebo ukončení aplikace.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a> Spustit ladění (F5), ale zpoždění spuštění aplikace  
 Můžete nastavit aplikaci spustit v režimu ladění, ale spusťte ji pomocí jiné metody než ladicí program. Můžete například, chcete-li ladit spuštění vaší aplikace z nabídky Start nebo chcete-li ladit proces na pozadí v aplikaci bez spuštění aplikace. Chcete-li zpoždění spuštění aplikace, postupujte takto:  
  
- Na **ladění** stránka vlastností aplikace (**ladění** v jazyce Visual C++ a JavaScript)  
  
  -   Pro aplikace Visual C# a Visual Basic, zvolte **nespouštět, ale ladit můj kód při spuštění**.  
  
  -   Pro aplikace Visual C++ a JavaScript, zvolte **Ano** z **spustit aplikaci** seznamu.  
  
- Zvolte **spustit ladění** na **ladění** nabídce (klávesnice: F5).  
  
- Aplikaci spusťte z nabídky Start, kontrakt provádění nebo jiný postup.  
  
  Spuštění aplikace v režimu ladění. Provádění pokračuje, dokud není dosaženo zarážky, můžete ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
  Další informace o ladění úlohy na pozadí, naleznete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UPW)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a> Spustit nainstalovanou aplikaci v ladicím programu  
Při spuštění ladění pomocí F5, Visual Studio vytvoří a nasadí aplikaci, nastaví aplikaci spustit v režimu ladění a pak spustí. Chcete-li spustit aplikaci, která je již nainstalována v zařízení, použijte **ladit nainstalovaný balíček aplikace** dialogové okno. Tento postup je užitečné, když budete chtít ladit aplikaci, která byla nainstalovaná z Microsoft Store, nebo když máte zdrojových souborů pro aplikace, ale není nutné projekt sady Visual Studio pro aplikaci. Například může mít vlastní sestavovací systém, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
Aplikaci můžete nainstalovat na místním zařízení, nebo může být na vzdáleném zařízení.  Aplikaci můžete spustit okamžitě, nebo můžete nastavit jeho spouštění v ladicím programu při spuštění jiným procesem nebo metody, například z nabídky Start nebo kontrakt aktivace, můžete také nastavit aplikaci spustit v režimu ladění, když chcete ladit proces na pozadí bez spuštění aplikace. Další informace najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UPW)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
Chcete-li spustit nainstalovanou aplikaci v ladicím programu, zvolte **ladění**, pak **jiné cíle ladění**a potom **ladit nainstalovaný balíček aplikace**. Další pokyny najdete v tématu [ladění balíčku nainstalované aplikace](../debugger/debug-installed-app-package.md).

###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Připojit ladicí modul k běžící aplikaci UPW  

Chcete-li ladit spuštěné aplikaci UPW, zvolte **ladění**, pak **jiné cíle ladění**a potom **ladit nainstalovaný balíček aplikace**. Další pokyny najdete v tématu [ladění balíčku nainstalované aplikace](../debugger/debug-installed-app-package.md).
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Připojit ladicí modul k běžící aplikaci Windows 8.x
 Připojit ladicí program [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace, musíte použít laditelný Správce balíčků pro nastavení aplikace pro spuštění v režimu ladění. Laditelný Správce balíčků se instaluje s nástroji Remote Tools for Visual Studio.  
  
 Připojování ladicího programu do aplikace je užitečné, když budete chtít ladit aplikace již nainstalována, jako je například aplikaci, která byla nainstalována ze [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. Připojení se vyžaduje, pokud mají zdrojové soubory pro aplikaci, ale není nutné projekt sady Visual Studio pro aplikaci. Například může mít vlastní sestavovací systém, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
 Připojování ladicího programu do aplikace vyžaduje tyto kroky:  
  
1.  Nastavte aplikaci spustit v režimu ladění. To je nutné provést při není aplikace spuštěna.  
  
2.  Spusťte aplikaci. Aplikaci můžete spustit z úvodní obrazovky, kontrakt provádění nebo některé jiné metody.  
  
3.  Připojte ladicí modul k běžící aplikaci.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> Nastavte aplikaci spustit v režimu ladění  
  
1.  Instalovat nástroje Remote Tools for Visual Studio na zařízení, ve kterém je aplikace nainstalovaná. Zobrazit [instalace vzdálených nástrojů](../debugger/remote-debugging.md).  
  
2.  Na obrazovce Start, vyhledejte `Debuggable Package Manager` a spusťte jej.  
  
     Zobrazí se okno prostředí PowerShell správně nakonfigurovaný pro rutiny AppxDebug.  
  
3.  Pokud chcete povolit ladění aplikace, je nutné zadat identifikátor Úplnýnázevbalíčku aplikace. Chcete-li zobrazit seznam všech aplikací, které zahrnuje Úplnýnázevbalíčku, zadejte `Get-AppxPackage` řádku Powershellu.  
  
4.  Na příkazovém řádku tento příkaz prostředí PowerShell, zadejte `Enable-AppxDebug` *PackageFullName* kde *PackageFullName* je identifikátor Úplnýnázevbalíčku aplikace.  
  
####  <a name="BKMK_Attach_the_debugger"></a> Připojit ladicí program  
 Připojení ladicího programu:  
  
1. Na **ladění** nabídce zvolte **připojit k procesu**.  
  
    **Připojit k procesu** zobrazí se dialogové okno.  
  
2. Připojit k aplikaci na vzdáleném zařízení, zadejte vzdáleného zařízení **kvalifikátor** pole. Můžeš:  
  
   -   Zadejte název do pole **kvalifikátor** pole.  
  
   -   Zvolte šipku dolů u **kvalifikátor** a pak vyberte zařízení ze seznamu zařízení, které jste připojili k před.  
  
   -   Zvolte **najít** vyberte zařízení ze seznamu zařízení v místní podsíti.  
  
3. Zadejte kód, který chcete ladit v **připojit k** pole.  
  
    Zvolte **vyberte** a udělejte jednu z následujících akcí:  
  
   -   Zvolte **automaticky určit typ kódu k ladění**  
  
   -   Zvolte **ladit tyto typy kódu** a ze seznamu vyberte jeden nebo více typů.  
  
4. V **procesy k dispozici** klikněte na položku procesu aplikace.  

   > [!NOTE]
   >  Na rozdíl od jiných typů aplikací jazyka JavaScript aplikace běžet instance wwahost.exe procesu. Pokud jiných aplikací jazyka JavaScript jsou spuštěny po připojení k aplikaci, musíte znát id číselné procesu (PID) wwahost.exe, na kterém aplikace běží v.  
   >   
   >  Zavřete všechny ostatní aplikace jazyka JavaScript je nejjednodušší způsob, jak zacházet s touto situací. Předtím, než spustíte aplikaci a poznamenejte si ID procesů wwahost.exe, v opačném případě můžete otevřít Správce úloh Windows. Pokud zadáte proces pro připojení v **procesy k dispozici** dialogovém okně wwahost.exe aplikace bude mít id, které se liší od těch, které jste si poznamenali.  
  
5. Zvolte **připojit**.  
  
   Visual Studio připojí ladicí program k procesu. Provádění pokračuje, dokud není dosaženo zarážky, můžete ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   