---
title: "Spusťte relaci ladění pro aplikace UWP v sadě Visual Studio (jazyka Visual Basic, C#, C++ a XAML) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
ms.openlocfilehash: c5c7cf9a5329e1b77d8669568434357deb2dd131
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio-vb-c-c-and-xaml"></a>Spusťte relaci ladění pro aplikace UWP v sadě Visual Studio (jazyka Visual Basic, C#, C++ a XAML)
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Toto téma popisuje, jak lze spustit relaci ladění pro aplikace UWP napsané v jazyce XAML a Visual C++, Visual C# nebo Visual Basic. Ladění aplikace zahrnuje konfiguraci relaci ladění i volba způsob a spusťte aplikaci.  
  
> [!NOTE]
>  Pro aplikace napsané v jazyce JavaScript a HTML najdete v části [spustit relaci ladění (JavaScript)](../debugger/start-a-debugging-session-for-store-apps-in-visual-studio-javascript.md).  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [Snadný způsob, jak spustit ladění](#BKMK_The_easy_way_to_start_debugging)  
  
 [Konfigurace relaci ladění](#BKMK_Configure_the_debugging_session)  
  
-   [Otevřít stránku vlastností ladění pro projekt](#BKMK_Open_the_debugging_property_page_for_the_project)  
  
-   [Vybrat možnosti konfigurace sestavení](#BKMK_Choose_the_build_configuration_options)  
  
-   [Vyberte cíl nasazení](#BKMK_Choose_the_deployment_target)  
  
-   [Zvolte používat ladicí program](#BKMK_Choose_the_debugger_to_use)  
  
-   [(Volitelné) Prodleva spuštění relace ladění](#BKMK__Optional__Delay_starting_the_debug_session)  
  
-   [(Volitelné) Zakázat vytváření zpětných smyček sítě](#BKMK__Optional__Disable_network_loopbacks)  
  
-   [(Volitelné) Znovu nainstalujte aplikaci při spuštění ladění](#BKMK__Optional__Reinstall_the_app_when_you_start_debugging)  
  
-   [(Volitelné) Zakázat ověřování požadavek na spuštění vzdáleného ladicího programu](#BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger)  
  
 [Spusťte relaci ladění](#BKMK_Start_the_debugging_session)  
  
-   [Spuštění ladění (F5)](#BKMK_Start_debugging__F5_)  
  
-   [Spuštění ladění (F5), ale zpoždění spuštění aplikace](#BKMK_Start_debugging__F5__but_delay_the_app_start)  
  
-   [Spuštění aplikace nainstalované v ladicím programu](#BKMK_Start_an_installed_app_in_the_debugger)  
  
-   [Připojí ladicí program ke spuštěné aplikaci](#BKMK_Attach_the_debugger_to_a_running_app_)  
  
    -   [Nastavit aplikaci spustit v režimu ladění](#BKMK_Set_the_app_to_run_in_debug_mode)  
  
    -   [Připojí ladicí program](#BKMK_Attach_the_debugger)  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a>Snadný způsob, jak spustit ladění  
  
1.  Otevřete aplikaci řešení v sadě Visual Studio.  
  
2.  Zvolte F5.  
  
 Visual Studio vytvoří a spustí aplikaci s ladicím programem připojen. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k výjimce zrušení zpracovat, nebo ukončení aplikace. Další informace najdete v tématu [přechod na relaci ladění (Xaml a C#)](../debugger/navigate-a-debugging-session-in-visual-studio-xaml-and-csharp.md) .  
  
##  <a name="BKMK_Configure_the_debugging_session"></a>Konfigurace relaci ladění  
  
###  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Otevřít stránku vlastností ladění pro projekt  
  
1.  V Průzkumníku řešení vyberte projekt. V místní nabídce vyberte **vlastnosti**.  
  
2.  Otevře se stránka vlastností ladění pro projekt to udělat:  
  
    -   Pro aplikace Visual C# a Visual Basic, zvolte **ladění**.  
  
         ![C &#35; &#47; Stránka vlastností ladění projektu jazyka Visual Basic](../debugger/media/dbg_csvb_debugpropertypage.png "DBG_CsVb_DebugPropertyPage")  
  
    -   Pro aplikace Visual C++, rozbalte **vlastnosti konfigurace** uzel a potom zvolte **ladění**.  
  
         ![C & č. 43; & č. 43; Stránka vlastností ladění aplikace pro UPW](../debugger/media/dbg_cpp_debugpropertypage.png "DBG_CPP_DebugPropertyPage")  
  
###  <a name="BKMK_Choose_the_build_configuration_options"></a>Vybrat možnosti konfigurace sestavení  
  
1.  Z **konfigurace** vyberte **ladění** nebo **(aktivní) ladicí**.  
  
2.  Z **platformy** seznamu zvolte cílovou platformu pro vývoj pro. Ve většině případů **libovolný procesor** (**všechny platformy** v jazyce Visual C++) je nejlepší volbou.  
  
###  <a name="BKMK_Choose_the_deployment_target"></a>Vyberte cíl nasazení  
 ![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Můžete nasadit a ladění aplikace UWP v sadě Visual Studio počítači, v simulátoru Visual Studio v místním počítači nebo na vzdáleném zařízení.  
  
-   Pro aplikace, C# a Visual Basic, vyberte cíl z **cílové zařízení** na seznamu **ladění** stránku vlastností projektu.  
  
-   Pro aplikace, C++, vyberte cíl z **ladicí program ke spuštění** na seznamu **ladění** stránky vlastností:  
  
 Vyberte jednu z těchto možností:  
  
|||  
|-|-|  
|**Místní počítač**|Ladění aplikace v aktuální relaci na místním počítači. V tématu [aplikace UWP spustit v místním počítači](../debugger/run-windows-store-apps-on-the-local-machine.md).|  
|**Simulátor**|Ladění aplikace v sadě Visual Studio simulátor pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace. Simulátor je plochy okno, které umožňuje ladit funkce zařízení – například touch gesta a otáčení zařízení – které nejsou k dispozici v místním počítači. V tématu [aplikace UWP spustit v simulátoru](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Vzdálený počítač**|Ladění aplikace na zařízení, které je připojený k místnímu počítači v síti intranet nebo přímo pomocí kabelu Ethernet. Chcete-li vzdáleně ladit, nástrojů pro vzdálenou Visual Studio musí být nainstalovaná a spuštěná na vzdáleném zařízení. V tématu [aplikace UWP spustit na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
  
 Pokud se rozhodnete **vzdáleného počítače**, zadejte název nebo IP adresu vzdáleného počítače v jednom z těchto způsobů:  
  
-   Zadejte název nebo IP adresu vzdáleného počítače.  
  
    -   Pro aplikace, C# a Visual Basic, zadejte název nebo IP adresa ve **vzdáleného počítače** pole.  
  
    -   Pro aplikace, C++, zadejte název nebo IP adresa ve **název počítače** pole.  
  
-   Zvolte ze vzdáleného počítače **vyberte připojení vzdáleného ladicího programu** dialogové okno.  
  
     Chcete-li otevřít dialogové okno:  
  
    -   Pro aplikace, C# a Visual Basic, zvolte **najít**.  
  
    -   U aplikací C++, zvolte na šipku dolů ve **název počítače** pole a zvolte  **\<vyhledejte... >**.  
  
     ![Dialogové okno Vyberte připojení vzdáleného ladicího programu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
    > [!NOTE]
    >  **Vyberte připojení vzdáleného ladicího programu** dialogové okno zobrazí počítače, které jsou na místním dílčí net a počítačů, které jsou připojeny přímo k sadě Visual Studio počítače pomocí kabelu Ethernet. Chcete-li určit jiný počítač, zadejte název v **název počítače** pole.  
  
 ![Platí pouze pro Windows Phone](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Můžete nasadit a ladění aplikace Windows Phone zařízení, nebo na jednom z emulátorů phone Visual Studio. Vyberte zařízení nebo emulátoru z **cílové zařízení** seznamu.  
  
###  <a name="BKMK_Choose_the_debugger_to_use"></a>Zvolte používat ladicí program  
 Ve výchozím nastavení Visual Studio debugs spravovaného kódu v C# a Visual Basic aplikace.  
  
 Pro aplikace, C# a Visual Basic můžete ladit jak spravovaná a nativní kód C/C++ v aplikaci. Vyberte **povolit ladění nespravovaného kódu** políčko, které chcete zahrnout do vaší relace ladění nativního kódu.  
  
 Ve výchozím nastavení Visual Studio debugs nativního kódu v aplikaci C++.  
  
 Pro aplikace, C++ můžete ladit konkrétní typy kódu, které jsou v součásti aplikace místo nebo kromě nativního kódu. Zadejte kód pro ladění v **ladicí program typu** na seznamu **ladění** stránce vlastností projektu aplikace.  
  
 Vyberte jednu z těchto ladicí programy z **proces aplikace** seznamu:  
  
|||  
|-|-|  
|**Pouze skriptu**|Ladění kódu jazyka JavaScript v aplikaci. Spravovaný kód a nativního kódu jsou ignorovány.|  
|**Jenom Native**|Ladění nativního kódu C/C++ ve vaší aplikaci. Spravovaný kód a kód jazyka JavaScript jsou ignorovány.|  
|**Jenom spravované**|Ladění spravovaného kódu v aplikaci. Kód jazyka JavaScript a nativního kódu C/C++ jsou ignorovány.|  
|**Ve smíšeném (spravovaná a nativní)**|Ladění nativního kódu C/C++ a spravovaného kódu v aplikaci. Kód jazyka JavaScript je ignorován.|  
|**Pouze GPU**|Ladění nativního kódu C++, která běží na grafický procesor (GPU).|  
  
 ![Platí pouze pro Windows Phone](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Pro aplikace Windows Phone, můžete také používat pro procesy na pozadí z ladicí program **zpracování úloh na pozadí**.  
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a>(Volitelné) Prodleva spuštění relace ladění  
 Ve výchozím nastavení sady Visual Studio okamžitě spustí aplikaci, při spuštění ladění. Můžete také spustit relaci ladění ale zpoždění spuštění vaší aplikace. Pokud vyberete tuto možnost, aplikace je spuštěn v ladicím programu při jeho spuštění z obrazovky Start nebo pomocí kontraktu aktivace nebo při spuštění jiným procesem nebo metoda. Můžete také zpoždění spuštění vaší aplikace, pokud chcete ladit úlohy na pozadí, pokud aplikace není spuštěna.  
  
 Chcete-li zpoždění spuštění vaší aplikace, můžete:  
  
-   Pro aplikace Visual C# a Visual Basic, vyberte **nespouštějí, ale po jeho spuštění ladění vlastního kódu** na **ladění** stránku vlastností.  
  
-   Pro aplikace Visual C++, zvolte **Ano** z **spustit aplikaci** seznam na **ladění** stránku vlastností.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a>(Volitelné) Zakázat vytváření zpětných smyček sítě  
 ![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Z bezpečnostních důvodů aplikace pro UPW, který je nainstalován standardním způsobem není dovoleno volání síťové zařízení, které je nainstalovaný. Ve výchozím nasazení sady Visual Studio vytvoří výjimku z tohoto pravidla pro aplikace nasazené. Tato výjimka umožňuje otestovat postupy komunikace na jednom počítači. Před odesláním v aplikaci Microsoft Store, měli byste otestovat aplikace bez výjimky.  
  
 Postup odebrání výjimky zpětné smyčky sítě:  
  
-   Pro aplikace Visual C# a Visual Basic, zrušte **povolit zpětné smyčky sítě** políčko **ladění** stránku vlastností.  
  
-   Pro aplikace Visual C++, zvolte **ne** z **povolit zpětné smyčky sítě** seznam na **ladění** stránku vlastností.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a>(Volitelné) Znovu nainstalujte aplikaci při spuštění ladění  
 K diagnostikování problémů s instalací a počáteční konfiguraci aplikace Visual C# nebo Visual Basic, zvolte **odinstalovat a znovu nainstalujte Můj balíček** na **ladění** znovu vytvořit na stránce vlastností původní instalace při spuštění ladění. Tato možnost není k dispozici pro projekty Visual C++.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a>(Volitelné) Zakázat ověřování požadavek na spuštění vzdáleného ladicího programu  
 ![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Ve výchozím nastavení je třeba zadat přihlašovací údaje ke spuštění vzdáleného ladicího programu.  
  
> [!IMPORTANT]
>  Můžete spustit vzdáleného ladicího programu v režimu bez ověřování, ale tento režim se důrazně nedoporučuje. Při spuštění v tomto režimu není žádné zabezpečení sítě. Na možnost Režim bez ověřování klikněte pouze v případě, že jste si jisti, že není síť ohrožena škodlivými nebo nevyžádanými daty.  
  
 Postup odebrání požadavek na ověření:  
  
1.  Pro aplikace Visual C# a Visual Basic, zrušte **ověřování** políčko **ladění** stránku vlastností.  
  
2.  Pro aplikace Visual C++, zvolte **ne** z **vyžadovat ověření** seznam na **ladění** stránku vlastností.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Start_the_debugging_session"></a>Spusťte relaci ladění  
  
###  <a name="BKMK_Start_debugging__F5_"></a>Spuštění ladění (F5)  
 Pokud vyberete **spustit ladění** (klávesové: F5) na **ladění** nabídce sady Visual Studio spustí aplikaci s ladicím programem připojen. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k výjimce, nebo ukončení aplikace.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>Spuštění ladění (F5), ale zpoždění spuštění aplikace  
 Můžete nastavit aplikaci spustit v režimu ladění, ale spusťte ji pomocí jiné metody než ladicího programu. Můžete například k ladění spuštění vaší aplikace z nabídky Start nebo k ladění proces na pozadí v aplikaci bez spuštění aplikace. Chcete-li zpoždění spuštění aplikace, postupujte takto:  
  
-   Na **ladění** stránka vlastností aplikace (**ladění** v jazyce Visual C++)  
  
    -   Pro aplikace Visual C# a Visual Basic, zvolte **nespouštějí, ale po jeho spuštění ladění vlastního kódu**.  
  
    -   Pro aplikace Visual C++, zvolte **Ano** z **spustit aplikaci** seznamu.  
  
-   Zvolte **spustit ladění** na **ladění** nabídky (klávesové: F5).  
  
-   Spusťte aplikaci z nabídky Start, provádění kontrakt, nebo pomocí jiné proceduře.  
  
 Spuštění aplikace v režimu ladění. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
 . Další informace o ladění úlohy na pozadí najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a>Spuštění aplikace nainstalované v ladicím programu  
 Při spuštění ladění pomocí F5, Visual Studio vytvoří a nasadí aplikaci, nastaví aplikaci spustit v režimu ladění a poté ji spustí. Spusťte aplikaci, která je již nainstalována na zařízení, použijte dialogové okno ladění nainstalován balíček aplikace. Tento postup je užitečný, pokud budete potřebovat k ladění aplikace, která byla nainstalována z Windows store, nebo pokud máte zdrojové soubory pro aplikace, ale nemáte projekt sady Visual Studio pro aplikaci. Například můžete mít systém vlastní sestavení, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
 Aplikace můžete nainstalovat na místním zařízení, nebo může být na vzdáleném zařízení.  Aplikaci můžete spustit okamžitě, nebo můžete nastavit jeho spuštění v ladicím programu při spuštění jiným procesem nebo metoda, například z nabídky Start nebo pomocí aktivace kontrakt, můžete také nastavit aplikaci spustit v režimu ladění, když chcete ladit procesy na pozadí. bez spuštění aplikace. Další informace najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
 Chcete-li nastavit nainstalovanou aplikaci spustit v režimu ladění, postupujte takto:  
  
> [!NOTE]
>  Při spuštění tento postup, nesmí být aplikace spuštěná.  
  
1.  Na **ladění** nabídce zvolte **ladění nainstalován balíček aplikace**  
  
2.  Ze seznamu vyberte jednu z následujících možností:  
  
    |||  
    |-|-|  
    |**Místní počítač**|Ladění aplikace v aktuální relaci na místním počítači. V tématu [aplikace UWP spustit v místním počítači](../debugger/run-windows-store-apps-on-the-local-machine.md).|  
    |**Simulátor**|Ladění aplikace v sadě Visual Studio simulátor pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace. Simulátor je plochy okno, které umožňuje ladit funkce zařízení – například touch gesta a otáčení zařízení – které nejsou k dispozici v místním počítači. V tématu [aplikace UWP spustit v simulátoru](../debugger/run-windows-store-apps-in-the-simulator.md).|  
    |**Vzdálený počítač**|Ladění aplikace na zařízení, které je připojený k místnímu počítači v síti intranet nebo přímo pomocí kabelu Ethernet. Chcete-li vzdáleně ladit, nástrojů pro vzdálenou Visual Studio musí být nainstalovaná a spuštěná na vzdáleném zařízení. V tématu [aplikace UWP spustit na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
  
3.  Vyberte si aplikaci z **nainstalované balíčky aplikací** seznamu.  
  
4.  Vyberte modul ladění z **ladění tento typ kódu** seznamu.  
  
5.  (Volitelné). Zvolte **nespouštějí, ale po jeho spuštění ladění vlastního kódu** k ladění aplikace, když se spustí jinou metodou nebo k ladění proces na pozadí.  
  
 Když kliknete na tlačítko **spustit**, aplikace je spuštěn nebo je nastaven na spouštění v režimu ladění.  
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>Připojí ladicí program ke spuštěné aplikaci  
 Připojit ladicí program na [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace, je nutné použít Debuggable správce balíčku se nastavit aplikaci spustit v režimu ladění. Debuggable Správce balíčků je nainstalován ve vzdálené nástroje sady Visual Studio.  
  
 Ladicí program se připojuje k aplikaci je užitečné, když potřebujete ladění aplikace již nainstalována, jako je například aplikace, ze kterého byla nainstalována [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. Připojení je požadovaná, když máte zdrojové soubory pro aplikace, ale nemáte projekt sady Visual Studio pro aplikaci. Například můžete mít systém vlastní sestavení, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
 Ladicí program se připojuje k aplikace vyžaduje tyto kroky:  
  
1.  Nastavte aplikaci spustit v režimu ladění. To je třeba provést, když není aplikace spuštěna.  
  
2.  Spusťte aplikaci. Aplikaci můžete spustit z obrazovky Start, provádění smlouva nebo jiné metody.  
  
3.  Připojí ladicí program na běžící aplikaci.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a>Nastavit aplikaci spustit v režimu ladění  
  
1.  Instalace nástrojů pro vzdálenou Visual Studio na zařízení, kde bude aplikace nainstalována. V tématu [instalace nástrojů pro vzdálenou](http://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools).  
  
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
  
5.  Zvolte **připojit**.  
  
 Visual Studio připojí ladicí program k procesu. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   
 [Přechod na relaci ladění (Xaml a C#)](../debugger/navigate-a-debugging-session-in-visual-studio-xaml-and-csharp.md)