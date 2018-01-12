---
title: "Spusťte relaci ladění pro aplikace UWP v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/04/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 66ec0e79-8261-4c19-a618-3fd1b3f71bbd
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 367fc334d0268a73e8ad1a33ebdc6e74036ddc86
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio"></a>Spusťte relaci ladění pro aplikace UWP v sadě Visual Studio
  
 Toto téma popisuje, jak lze spustit relaci ladění pro aplikace UWP napsané v jazyce XAML a Visual C++, Visual C# nebo Visual Basic a pro aplikace UWP napsané v HTML a JavaScript. Ladění aplikace zahrnuje konfiguraci relaci ladění i volba způsob a spusťte aplikaci.  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a>Snadný způsob, jak spustit ladění  
  
1.  Otevřete aplikaci řešení v sadě Visual Studio.  
  
2.  Zvolte F5.  
  
 Visual Studio vytvoří a spustí aplikaci s ladicím programem připojen. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
##  <a name="BKMK_Choose_the_build_configuration_options"></a>Vybrat možnosti konfigurace sestavení  
  
1.   Z rozevíracího seznamu vedle položky **spustit ladění** tlačítko ladicí program **standardní** nástrojů vyberte **ladění**.  
  
2.  Z **platformy** seznamu zvolte cílovou platformu pro vývoj pro.  
  
##  <a name="BKMK_Choose_the_deployment_target"></a>Vyberte cíl nasazení  
  
Můžete nasadit a ladění aplikace UWP na počítač sadě Visual Studio, připojené zařízení, simulátoru Visual Studio na místním počítači, vzdáleném zařízení nebo emulátor. Vyberte cíl nasazení z rozevíracího seznamu vedle **platformy** cíl ladicí program **standardní** panelu nástrojů.
  
![Vyberte cíl nasazení](../debugger/media/vsrun_select_target_device.png)  
  
Vyberte jednu z těchto možností:  
  
|||  
|-|-|  
|**Místní počítač**|Ladění aplikace v aktuální relaci na místním počítači.|  
|**Simulátor**|Ladění aplikace v simulátoru Visual Studio pro UPW a [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace. Simulátor je plochy okno, které umožňuje ladit funkce zařízení – například touch gesta a otáčení zařízení –, nemusí být k dispozici v místním počítači. Tato možnost je k dispozici, pouze pokud vaše aplikace **cílové platformy Min. Verze** je menší než nebo rovna operační systém na vývojovém počítači. V tématu [aplikace UWP spustit v simulátoru](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Vzdálený počítač**|Ladění aplikace na zařízení, které je připojený k místnímu počítači v síti intranet nebo přímo pomocí kabelu Ethernet. Chcete-li vzdáleně ladit, nástrojů pro vzdálenou pro sadu Visual Studio musí být nainstalovaná a spuštěná na vzdáleném zařízení. V tématu [aplikace UWP spustit na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
|**Zařízení**|Ladění aplikace na zařízení připojená k portu USB. Zařízení musí být vývojáře odemčený a obrazovku odemknout.|  
|**Emulátoru mobilního**|Spouštěcí emulátoru se zadaným v názvu emulátoru, nasaďte aplikaci a spustit ladění. Emulátorů jsou dostupné jenom na počítače Hyper-V, které jsou povolena systémem Windows 8.1 nebo novější verze.|  

##  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Zvolit další možnosti ladění  

Pokud potřebujete nakonfigurovat další možnosti ladění, otevřete její stránku vlastností projektu.
  
1.  V Průzkumníku řešení vyberte projekt. V místní nabídce vyberte **vlastnosti**.  
  
2.  Otevře se stránka vlastností ladění pro projekt to udělat:  
  
    -   Pro aplikace Visual C# a Visual Basic, zvolte **ladění**.  
  
         ![C & #35; & #47; Stránka vlastností ladění projektu jazyka Visual Basic](../debugger/media/dbg_csvb_debugpropertypage.png)  
  
    -   Pro aplikace Visual C++ a JavaScript, rozbalte **vlastnosti konfigurace** uzel a potom zvolte **ladění**.  
  
         ![C & č. 43; & č. 43; Stránky vlastností ladění aplikace UWP](../debugger/media/dbg_cpp_debugpropertypage.png)  

###  <a name="BKMK_Choose_the_debugger_to_use"></a>Zvolte používat ladicí program  
Ve výchozím nastavení Visual Studio debugs spravovaného kódu v C# a Visual Basic aplikace. Pro aplikace, C# a Visual Basic můžete ladit jak spravovaná a nativní kód C/C++ v aplikaci. V aplikacích C++ Visual Studio debugs nativního kódu ve výchozím nastavení. V aplikacích jazyka JavaScript Visual Studio debugs skriptu ve výchozím nastavení. 
  
U aplikací C++, JavaScript můžete ladit konkrétní typy kódu, které jsou v součásti aplikace místo nebo kromě nativního kódu. Zadejte kód pro ladění v **ladicí program typu** na seznamu **ladění** stránce vlastností projektu aplikace.  
  
Vyberte jednu z těchto ladicí programy z **proces aplikace** seznamu:  
  
|||  
|-|-|  
|**Jenom spravované**|Ladění spravovaného kódu v aplikaci. Kód jazyka JavaScript a nativního kódu C/C++ jsou ignorovány.|  
|**Jenom Native**|Ladění nativního kódu C/C++ ve vaší aplikaci. Spravovaný kód a kód jazyka JavaScript jsou ignorovány.|  
|**Ve smíšeném (spravovaná a nativní)**|Ladění nativního kódu C/C++ a spravovaného kódu v aplikaci. Kód jazyka JavaScript je ignorován. V projektech C++, tato možnost nazývá **(spravované a nativní)**.|  
|**Pouze skriptu**|Ladění kódu jazyka JavaScript v aplikaci. Spravovaný kód a nativního kódu jsou ignorovány.|  
|**Skript a nativní**|Ladění nativního kódu C/C++ a kód jazyka JavaScript v aplikaci. Spravovaný kód je ignorován. Chcete-li k dispozici v projektech C++ jenom.|  
|**Pouze GPU (C++ AMP)**|Ladění nativního kódu C++, která běží na grafický procesor (GPU). Chcete-li k dispozici v projektech C++ jenom.|  

V aplikacích jazyka C# a Visual Basic, můžete také nastavit stejné **ladicího programu typ** hodnoty pro všechny úlohy na pozadí, které jsou součástí projektu.
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a>(Volitelné) Prodleva spuštění relace ladění  
 Ve výchozím nastavení sady Visual Studio okamžitě spustí aplikaci, při spuštění ladění. Můžete také spustit relaci ladění ale zpoždění spuštění vaší aplikace. Pokud vyberete tuto možnost, aplikace je spuštěn v ladicím programu při jeho spuštění z obrazovky Start nebo pomocí kontraktu aktivace nebo při spuštění jiným procesem nebo metoda. Můžete také zpoždění spuštění vaší aplikace, pokud chcete ladit úlohy na pozadí, pokud aplikace není spuštěna.  
  
 Chcete-li zpoždění spuštění vaší aplikace, můžete:  
  
-   Pro aplikace Visual C# a Visual Basic, vyberte **nespouštějí, ale po jeho spuštění ladění vlastního kódu** na **ladění** stránku vlastností.  
  
-   Pro aplikace Visual C++ a JavaScript, zvolte **Ano** z **spustit aplikaci** na seznamu **ladění** stránku vlastností.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a>(Volitelné) Zakázat vytváření zpětných smyček sítě  
  
 Z bezpečnostních důvodů aplikace pro UPW, který je nainstalován standardním způsobem není dovoleno volání síťové zařízení, které je nainstalovaný. Ve výchozím nasazení sady Visual Studio vytvoří výjimku z tohoto pravidla pro aplikace nasazené. Tato výjimka umožňuje otestovat postupy komunikace na jednom počítači. Před odesláním v aplikaci Microsoft Store, měli byste otestovat aplikace bez výjimky.  
  
 Postup odebrání výjimky zpětné smyčky sítě:  
  
-   Pro aplikace Visual C# a Visual Basic, zrušte **Povolit místní sítě zpětné smyčky** políčko **ladění** stránku vlastností.  
  
-   Pro aplikace Visual C++ a JavaScript, zvolte **ne** z **Povolit místní sítě smyčky** seznam na **ladění** stránku vlastností.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a>(Volitelné) Znovu nainstalujte aplikaci při spuštění ladění  
 K diagnostikování problémů s instalací a počáteční konfiguraci aplikace Visual C# nebo Visual Basic, zvolte **odinstalovat a znovu nainstalujte Můj balíček** na **ladění** znovu vytvořit na stránce vlastností původní instalace při spuštění ladění. Tato možnost není k dispozici pro projekty Visual C++ a JavaScript.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a>(Volitelné) Zakázat ověřování požadavek na spuštění vzdáleného ladicího programu  
  
 Ve výchozím nastavení, musíte zadat přihlašovací údaje ke spuštění vzdáleného ladicího programu, když vyberete **vzdáleného počítače** jako cíl nasazení.
  
> [!IMPORTANT]
>  Můžete spustit vzdáleného ladicího programu s bez ověřování, ale tento režim se důrazně nedoporučuje. Při spuštění v tomto režimu není žádné zabezpečení sítě. Zvolte bez ověřování pouze v případě, že jste si jisti, že síť není riziku škodlivý kód nebo nepřátelských přenosů.  
  
 Postup odebrání požadavek na ověření:  
  
1.  Pro aplikace Visual C# a Visual Basic, vyberte **vzdáleného počítače** jako **cílové zařízení** na **ladění** stránku vlastností a pak nastavte **režim ověřování ** k **žádné** nebo **Universal (nešifrovaného protokolu)**.
  
2.  U aplikací Visual C++ a JavaScript vyberte **vzdáleného počítače** jako **cílové zařízení** na **ladění** stránku vlastností a pak nastavte **vyžadují Ověřování** k **žádné** nebo **Universal (nešifrovaného protokolu)**.  

    **Univerzální (nešifrovaného protokolu)** je určen pro použití při nasazování na vzdáleném zařízení. V současné době je to pro zařízení IoT, zařízení, Xbox a HoloLens zařízení, a také Creators aktualizace nebo novější počítače. Univerzální (nešifrovaného protokolu) lze používat pouze v důvěryhodných sítích. Ladění připojení je zranitelný vůči uživateli se zlými úmysly kteří může zachytávat a měnit data, které jsou předávány mezi vývoj a vzdáleného počítače.  
  
##  <a name="BKMK_Start_the_debugging_session"></a>Spusťte relaci ladění  
  
###  <a name="BKMK_Start_debugging__F5_"></a>Spuštění ladění (F5)  
 Pokud vyberete **spustit ladění** (klávesové: F5) na **ladění** nabídce sady Visual Studio spustí aplikaci s ladicím programem připojen. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k výjimce, nebo ukončení aplikace.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>Spuštění ladění (F5), ale zpoždění spuštění aplikace  
 Můžete nastavit aplikaci spustit v režimu ladění, ale spusťte ji pomocí jiné metody než ladicího programu. Můžete například k ladění spuštění vaší aplikace z nabídky Start nebo k ladění proces na pozadí v aplikaci bez spuštění aplikace. Chcete-li zpoždění spuštění aplikace, postupujte takto:  
  
-   Na **ladění** stránka vlastností aplikace (**ladění** v jazycích Visual C++ a JavaScript)  
  
    -   Pro aplikace Visual C# a Visual Basic, zvolte **nespouštějí, ale po jeho spuštění ladění vlastního kódu**.  
  
    -   Pro aplikace Visual C++ a JavaScript, zvolte **Ano** z **spustit aplikaci** seznamu.  
  
-   Zvolte **spustit ladění** na **ladění** nabídky (klávesové: F5).  
  
-   Spusťte aplikaci z nabídky Start, provádění kontrakt, nebo pomocí jiné proceduře.  
  
 Spuštění aplikace v režimu ladění. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
 . Další informace o ladění úlohy na pozadí najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a>Spuštění aplikace nainstalované v ladicím programu  
Při spuštění ladění pomocí F5, Visual Studio vytvoří a nasadí aplikaci, nastaví aplikaci spustit v režimu ladění a poté ji spustí. Chcete-li spustit aplikaci, která je již nainstalována na zařízení, použijte **ladění nainstalován balíček aplikace** dialogové okno. Tento postup je užitečný, pokud budete potřebovat k ladění aplikace, která byla nainstalována z Microsoft Store, nebo když máte zdrojové soubory pro aplikace, ale nemáte projekt sady Visual Studio pro aplikaci. Například můžete mít systém vlastní sestavení, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
Aplikace můžete nainstalovat na místním zařízení, nebo může být na vzdáleném zařízení.  Aplikaci můžete spustit okamžitě, nebo můžete nastavit jeho spuštění v ladicím programu při spuštění jiným procesem nebo metoda, například z nabídky Start nebo pomocí aktivace kontrakt, můžete také nastavit aplikaci spustit v režimu ladění, když chcete ladit procesy na pozadí. bez spuštění aplikace. Další informace najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
Chcete-li nainstalovanou aplikaci spustit v ladicím programu, zvolte **ladění**, pak **jiné cíle ladění**a potom **ladění nainstalován balíček aplikace**. Další pokyny najdete v tématu [ladění balíček nainstalovanou aplikaci](../debugger/debug-installed-app-package.md).

> [!NOTE]
> Pro Windows 8.1, zvolte **ladění**a potom zvolte **ladění nainstalován balíček aplikace**.

###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>Připojí ladicí program k spuštěné aplikaci UWP  

Ladění spuštěné aplikace UPW, zvolte **ladění**, pak **jiné cíle ladění**a potom **ladění nainstalován balíček aplikace**. Další pokyny najdete v tématu [ladění balíček nainstalovanou aplikaci](../debugger/debug-installed-app-package.md).
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>Připojí ladicí program do spuštěné aplikace pro Windows 8.x
 Připojit ladicí program na [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace, je nutné použít Debuggable správce balíčku se nastavit aplikaci spustit v režimu ladění. Debuggable Správce balíčků je nainstalován ve nástroje Remote Tools pro sadu Visual Studio.  
  
 Ladicí program se připojuje k aplikaci je užitečné, když potřebujete ladění aplikace již nainstalována, jako je například aplikace, ze kterého byla nainstalována [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. Připojení je požadovaná, když máte zdrojové soubory pro aplikace, ale nemáte projekt sady Visual Studio pro aplikaci. Například můžete mít systém vlastní sestavení, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
 Ladicí program se připojuje k aplikace vyžaduje tyto kroky:  
  
1.  Nastavte aplikaci spustit v režimu ladění. To je třeba provést, když není aplikace spuštěna.  
  
2.  Spusťte aplikaci. Aplikaci můžete spustit z obrazovky Start, provádění smlouva nebo jiné metody.  
  
3.  Připojí ladicí program na běžící aplikaci.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a>Nastavit aplikaci spustit v režimu ladění  
  
1.  Instalace nástrojů pro vzdálenou pro sadu Visual Studio na zařízení, kde bude aplikace nainstalována. V tématu [instalace nástrojů pro vzdálenou](../debugger/remote-debugging.md).  
  
2.  Na obrazovce Start vyhledejte `Debuggable Package Manager` a spusťte ho.  
  
     Zobrazí se okno prostředí PowerShell správně nakonfigurovaný pro rutinu AppxDebug.  
  
3.  Chcete-li povolit ladění aplikace, musíte zadat identifikátor PackageFullName aplikace. Chcete-li zobrazit seznam všech aplikací, které zahrnuje PackageFullName, zadejte `Get-AppxPackage` v příkazovém řádku prostředí PowerShell.  
  
4.  Do příkazového řádku Powershellu, zadejte `Enable-AppxDebug` *PackageFullName* kde *PackageFullName* je identifikátor PackageFullName aplikace.  
  
####  <a name="BKMK_Attach_the_debugger"></a>Připojí ladicí program  
 Připojit ladicí program:  
  
1.  Na **ladění** nabídce zvolte **připojit k procesu**.  
  
     **Připojit k procesu** zobrazí se dialogové okno.  
  
2.  Připojit k aplikaci na vzdáleném zařízení, zadejte vzdáleného zařízení v **kvalifikátor** pole. Můžeš:  
  
    -   Zadejte název do pole **kvalifikátor** pole.  
  
    -   Vyberte šipku dolů v **kvalifikátor** pole a pak vyberte ze seznamu zařízení, které jste připojili k před zařízení.  
  
    -   Zvolte **najít** vyberte zařízení ze seznamu zařízení v místní podsíti.  
  
3.  Zadejte typ kód, který chcete ladit v **přiřadit** pole.  
  
     Zvolte **vyberte** a pak udělejte jednu z následujících akcí:  
  
    -   Zvolte **automaticky určit typ kódu k ladění**  
  
    -   Zvolte **ladění tyto typy kódu** a potom vyberte jeden nebo více typů ze seznamu.  
  
4.  V **dostupné procesy** vyberte procesu aplikací.  

    > [!NOTE]
    >  Na rozdíl od jiných typů aplikací JavaScript aplikace běžet v instanci procesu wwahost.exe. Pokud jiné aplikace JavaScript běží při připojení k aplikaci, musíte vědět, id procesu číselné (PID) wwahost.exe kterém aplikace běží v.  
    >   
    >  Nejjednodušší způsob, jak řešení této situace je zavřete všechny ostatní aplikace JavaScript. Předtím, než spustíte aplikaci a poznamenejte si ID wwahost.exe procesů, jinak můžete otevřít Správce úloh systému Windows. Pokud zadáte na připojení k v procesu **dostupné procesy** dialogové okno, wwahost.exe aplikace bude mít id, které se liší od těch, které jste si poznamenali.  
  
5.  Zvolte **připojit**.  
  
 Visual Studio připojí ladicí program k procesu. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   