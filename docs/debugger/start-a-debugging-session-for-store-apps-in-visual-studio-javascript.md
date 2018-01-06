---
title: "Spusťte relaci ladění pro aplikace UWP v sadě Visual Studio (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: fb91203f-2cf4-44d3-8ed9-93bc5aaa50b8
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: b92f2f5ac10f917257e58443ab2161a164f39b28
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="start-a-debugging-session-for-uwp-apps-in-visual-studio-javascript"></a>Spusťte relaci ladění pro aplikace UWP v sadě Visual Studio (JavaScript)
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Toto téma popisuje, jak lze spustit relaci ladění pro aplikace UWP napsané v jazyce HTML5 a používání jazyka JavaScript. Můžete spustit ladění pomocí jednoho klávesu, nebo můžete nakonfigurovat relaci ladění u konkrétních scénářů a pak zvolte, jakým způsobem a spusťte aplikaci.  
  
> [!NOTE]
>  Pro aplikace napsané v jazyce XAML a Visual C#, Visual C++ nebo Visual Basic, najdete v části [spustit relaci ladění (jazyka Visual Basic, C#, C++ a XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [V tomto tématu](#BKMK_In_this_topic)  
  
 [Snadný způsob, jak spustit ladění](#BKMK_The_easy_way_to_start_debugging)  
  
 [Konfigurace relaci ladění](#BKMK_Configure_the_debugging_session)  
  
-   [Otevřít stránku vlastností ladění pro projekt](#BKMK_Open_the_debugging_property_page_for_the_project)  
  
-   [Vybrat možnosti konfigurace sestavení](#BKMK_Choose_the_build_configuration_options)  
  
-   [Vyberte cíl nasazení](#BKMK_Choose_the_deployment_target)  
  
-   [Zvolte používat ladicí program](#BKMK_Choose_the_debugger_to_use)  
  
-   [(Volitelné) Zpoždění spuštění aplikace v relaci ladění](#BKMK__Optional__Delay_starting_app_in_the_debug_session)  
  
-   [(Volitelné) Zakázat vytváření zpětných smyček sítě](#BKMK__Optional__Disable_network_loopbacks)  
  
 [Spusťte relaci ladění](#BKMK_Start_the_debugging_session)  
  
-   [Spuštění ladění (F5)](#BKMK_Start_debugging__F5_)  
  
-   [Spuštění ladění (F5), ale zpoždění spuštění aplikace](#BKMK_Start_debugging__F5__but_delay_the_app_start)  
  
 [Spuštění aplikace nainstalované v ladicím programu](#BKMK_Start_an_installed_app_in_the_debugger)  
  
 [Připojí ladicí program ke spuštěné aplikaci](#BKMK_Attach_the_debugger_to_a_running_app_)  
  
-   [Nastavit aplikaci spustit v režimu ladění](#BKMK_Set_the_app_to_run_in_debug_mode)  
  
-   [Připojí ladicí program](#BKMK_Attach_the_debugger)  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a>Snadný způsob, jak spustit ladění  
 ![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
1.  Otevřete aplikaci řešení v sadě Visual Studio.  
  
2.  Pokud řešení obsahuje více projektů, ujistěte se, že projekt, který chcete ladit je spuštění projektu. V řešení prozkoumat, vyberte projekt a potom zvolte **nastavit jako spouštěný projekt** v místní nabídce.  
  
3.  Stiskněte klávesu F5.  
  
 ![Platí pouze pro Windows Phone](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Visual Studio vytvoří a spustí aplikaci s ladicím programem připojen. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace. Další informace najdete v tématu [rychlý úvod: ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md).  
  
##  <a name="BKMK_Configure_the_debugging_session"></a>Konfigurace relaci ladění  
 Vzhledem k tomu, že skript není kompilovat, nastavení konfigurace a platformy sestavení se nevztahují. Pokud ladíte C++ nebo spravované součásti, nastavte **konfigurace** k **ladění** a zvolte svou cílovou platformu z **konfigurace** dialogové okno.  
  
###  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Otevřít stránku vlastností ladění pro projekt  
  
1.  V Průzkumníku řešení vyberte projekt. V místní nabídce vyberte **vlastnosti**.  
  
2.  Rozbalte **vlastnosti konfigurace** uzel a potom zvolte **ladění**.  
  
###  <a name="BKMK_Choose_the_build_configuration_options"></a>Vybrat možnosti konfigurace sestavení  
  
1.  Z **konfigurace** vyberte **ladění** nebo **(aktivní) ladicí**.  
  
2.  Z **platformy** seznamu zvolte cílovou platformu pro vývoj pro. Ve většině případů **libovolný procesor** je nejlepší volbou.  
  
###  <a name="BKMK_Choose_the_deployment_target"></a>Vyberte cíl nasazení  
 Můžete nasadit a ladění aplikace v sadě Visual Studio počítači, v simulátoru Visual Studio v místním počítači nebo ve vzdáleném počítači. Zvolte cíle z **ladicí program ke spuštění** na seznamu **ladění** stránku vlastností projektu.  
  
 ![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Pro aplikace pro UPW, vyberte jednu z těchto možností z **cílové zařízení** seznamu:  
  
|||  
|-|-|  
|**Místní počítač**|Ladění aplikace v aktuální relaci na místním počítači. V tématu [aplikace UWP spustit v místním počítači](../debugger/run-windows-store-apps-on-the-local-machine.md).|  
|**Simulátor**|Ladění aplikace v sadě Visual Studio simulátor pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace. Simulátor je plochy okno, které umožňuje ladit funkce zařízení – například touch gesta a otáčení zařízení – které nejsou k dispozici v místním počítači. V tématu [aplikace UWP spustit v simulátoru](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Vzdálený počítač**|Ladění aplikace na zařízení, které je připojený k místnímu počítači v síti intranet nebo přímo pomocí kabelu Ethernet. Chcete-li vzdáleně ladit, nástrojů pro vzdálenou Visual Studio musí být nainstalovaná a spuštěná na vzdáleném zařízení. V tématu [aplikace UWP spustit na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
  
 Pokud se rozhodnete **vzdáleného počítače**, zadejte název nebo IP adresu vzdáleného počítače v jednom z těchto způsobů:  
  
-   Zadejte název nebo IP adresu vzdáleného počítače v **název počítače** pole.  
  
-   Vyberte šipku dolů ve **název počítače** pole a zvolte  **\<vyhledejte... >**. Zvolte vzdáleného počítače z **vyberte připojení vzdáleného ladicího programu** dialogové okno.  
  
     ![Vyberte připojení vzdáleného ladicího programu](../debugger/media/vsrun_pro_selectremotedebuggerdlg.png "VSRUN_PRO_SelectRemoteDebuggerDlg")  
  
    > [!NOTE]
    >  Dialogové okno vybrat připojení vzdáleného ladicího programu zobrazí počítače, které jsou na místním dílčí net a počítačů, které jsou připojeny přímo k sadě Visual Studio počítače pomocí kabelu Ethernet. Chcete-li určit jiný počítač, zadejte název v **název počítače** pole.  
  
 ![Platí pouze pro Windows Phone](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Pro aplikace Windows Phone, zvolte **zařízení** nebo jeden z emulátorů z **cílové zařízení** seznamu.  
  
###  <a name="BKMK_Choose_the_debugger_to_use"></a>Zvolte používat ladicí program  
 Ve výchozím nastavení připojí ladicí program k kód jazyka JavaScript v aplikaci. Můžete k ladění nativního C++ a spravovaný kód součástí aplikace místo kód jazyka JavaScript. Zadejte kód pro ladění v **ladicí program typu** na seznamu **ladění** stránce vlastností projektu aplikace.  
  
 Vyberte jednu z těchto ladicí programy z **ladicí program typu** seznamu:  
  
|||  
|-|-|  
|**Pouze skriptu**|Ladění kódu jazyka JavaScript v aplikaci. Spravovaný kód a nativního kódu jsou ignorovány.|  
|**Jenom Native**|Ladění nativního kódu C/C++ ve vaší aplikaci. Spravovaný kód a kód jazyka JavaScript jsou ignorovány.|  
|**Nativní pomocí skriptu**|Ladění nativního kódu C++ a kód jazyka JavaScript v aplikaci.|  
|**Jenom spravované**|Ladění spravovaného kódu v aplikaci. Kód jazyka JavaScript a nativního kódu C/C++ jsou ignorovány.|  
|**Ve smíšeném (spravovaná a nativní)**|Ladění nativního kódu C/C++ a spravovaného kódu v aplikaci. Kód jazyka JavaScript je ignorován.|  
  
###  <a name="BKMK__Optional__Delay_starting_app_in_the_debug_session"></a>(Volitelné) Zpoždění spuštění aplikace v relaci ladění  
 Ve výchozím nastavení sady Visual Studio okamžitě spustí aplikaci, při spuštění ladění. Můžete také spustit relaci ladění ale zpoždění spuštění vaší aplikace. Spuštění aplikace v ladicím programu při jeho spuštění z nabídky Start nebo pomocí aktivace kontrakt, nebo když je spuštěno jiným procesem nebo metoda. Můžete taky zpožděné spuštění ladění pozadí události ve vaší aplikaci, kterou chcete dojít, když není aplikace spuštěna.  
  
 Můžete určit, zda zpoždění spuštění aplikace v rámci **spustit aplikaci** seznam na **ladění** stránce vlastností projektu aplikace. Vyberte jednu z těchto možností:  
  
-   Zvolte **ne** zpoždění spuštění vaší aplikace.  
  
-   Zvolte **Ano** okamžitě spusťte aplikaci.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a>(Volitelné) Zakázat vytváření zpětných smyček sítě  
 ![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Z bezpečnostních důvodů aplikace pro UPW, který je nainstalován standardním způsobem není dovoleno volání síťové zařízení, které je nainstalovaný. Ve výchozím nasazení sady Visual Studio vytvoří výjimku z tohoto pravidla pro aplikace nasazené. Tato výjimka umožňuje otestovat postupy komunikace na jednom počítači. Před odesláním v aplikaci Microsoft Store, měli byste otestovat aplikace bez výjimky.  
  
 Odebrat výjimku sítě zpětné smyčky, zvolte **ne** z **povolit zpětné smyčky sítě** seznam na **ladění** stránku vlastností.  
  
##  <a name="BKMK_Start_the_debugging_session"></a>Spusťte relaci ladění  
  
###  <a name="BKMK_Start_debugging__F5_"></a>Spuštění ladění (F5)  
 Pokud vyberete **spustit ladění** na **ladění** nabídky (klávesové: F5), Visual Studio spustí aplikaci s ladicím programem připojen. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>Spuštění ladění (F5), ale zpoždění spuštění aplikace  
 Můžete nastavit aplikaci spustit v režimu ladění, ale nechat ji spustit pomocí jiné metody než ladicího programu. Můžete například k ladění spuštění vaší aplikace z nabídky Start nebo k ladění proces na pozadí v aplikaci bez spuštění aplikace. Chcete-li zpoždění spuštění aplikace, postupujte takto:  
  
1.  Na **ladění** stránky aplikace projektu vlastnosti, vyberte **ne** z **spustit aplikaci** seznamu.  
  
2.  Zvolte **spustit ladění** na **ladění** nabídky (klávesové: F5).  
  
3.  Spusťte aplikaci z nabídky Start, provádění kontrakt, nebo pomocí jiné proceduře.  
  
 Spuštění aplikace v režimu ladění. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
 . Další informace o ladění úlohy na pozadí najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
##  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a>Spuštění aplikace nainstalované v ladicím programu  
 Při spuštění ladění pomocí F5, Visual Studio vytvoří a nasadí aplikaci, nastaví aplikaci spustit v režimu ladění a poté ji spustí. Spusťte aplikaci, která je již nainstalována na zařízení, použijte dialogové okno ladění nainstalován balíček aplikace. Tento postup je užitečný, pokud budete potřebovat k ladění aplikace, která byla nainstalována z Windows store, nebo pokud máte zdrojové soubory pro aplikace, ale nemáte projekt sady Visual Studio pro aplikaci. Například můžete mít systém vlastní sestavení, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
 Aplikace můžete nainstalovat na místním zařízení, nebo může být na vzdáleném zařízení.  Aplikaci můžete spustit okamžitě, nebo můžete nastavit jeho spuštění v ladicím programu při spuštění jiným procesem nebo metoda, například z nabídky Start nebo pomocí aktivace kontrakt, můžete také nastavit aplikaci spustit v režimu ladění, když chcete ladit procesy na pozadí. bez spuštění aplikace. Další informace najdete v tématu [aktivační události pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
 Chcete-li nastavit nainstalovanou aplikaci spustit v režimu ladění, postupujte takto:  
  
> [!NOTE]
>  Při spuštění tento postup, nesmí být aplikace spuštěná.  
  
1.  Na **ladění** nabídce zvolte **ladění nainstalován balíček aplikace**.  
  
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
  
##  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>Připojí ladicí program ke spuštěné aplikaci  
 Připojit ladicí program na [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace, je nutné použít Debuggable správce balíčku se nastavit aplikaci spustit v režimu ladění. Debuggable Správce balíčků je nainstalován ve vzdálené nástroje sady Visual Studio.  
  
 Ladicí program se připojuje k aplikaci je užitečné, když potřebujete ladění aplikace již nainstalována, jako je například aplikace, která byla nainstalována z Windows uložit. Připojení je požadovaná, když máte zdrojové soubory pro aplikace, ale nemáte projekt sady Visual Studio pro aplikaci. Například můžete mít systém vlastní sestavení, který nepoužívá projektů sady Visual Studio nebo řešení.  
  
 Připojit k aplikaci:  
  
1.  Nastavte aplikaci spustit v režimu ladění. To je třeba provést, když není aplikace spuštěna.  
  
2.  Spusťte aplikaci. Aplikaci můžete spustit z nabídky Start, provádění smlouva nebo jiné metody.  
  
3.  Připojí ladicí program na běžící aplikaci.  
  
###  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a>Nastavit aplikaci spustit v režimu ladění  
  
1.  Instalace nástrojů pro vzdálenou Visual Studio na zařízení, kde bude aplikace nainstalována. V tématu [instalace nástrojů pro vzdálenou](http://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools).  
  
2.  V nabídce Start vyhledejte `Debuggable Package Manager` a spusťte ho.  
  
     Zobrazí se okno prostředí PowerShell správně nakonfigurovaný pro rutinu AppxDebug.  
  
3.  Chcete-li povolit ladění aplikace, musíte zadat identifikátor PackageFullName aplikace. Chcete-li zobrazit seznam všech aplikací, které zahrnuje PackageFullName, zadejte `Get-AppxPackage` v příkazovém řádku prostředí PowerShell.  
  
4.  Do příkazového řádku Powershellu, zadejte `Enable-AppxDebug` *PackageFullName* kde *PackageFullName* je identifikátor PackageFullName aplikace.  
  
###  <a name="BKMK_Attach_the_debugger"></a>Připojí ladicí program  
  
> [!TIP]
>  Aplikace JavaScript běžet v instanci procesu wwahost.exe. Pokud jiné aplikace JavaScript běží při připojení k aplikaci, musíte vědět, id procesu číselné (PID) wwahost.exe kterém aplikace běží v.  
>   
>  Nejjednodušší způsob, jak řešení této situace je zavřete všechny ostatní aplikace JavaScript. Předtím, než spustíte aplikaci a poznamenejte si ID wwahost.exe procesů, jinak můžete otevřít Správce úloh systému Windows. Pokud zadáte na připojení k v procesu **dostupné procesy** dialogové okno, wwahost.exe aplikace bude mít id, které se liší od těch, které jste si poznamenali.  
  
 Připojit ladicí program:  
  
1.  Na **ladění** nabídce zvolte **připojit k procesu**.  
  
     **Připojit k procesu** zobrazí se dialogové okno.  
  
2.  Připojit k aplikaci na vzdáleném zařízení, zadejte vzdáleného zařízení v **kvalifikátor** pole. Můžeš:  
  
    -   Zadejte název do pole **kvalifikátor** pole.  
  
    -   Vyberte šipku dolů v **kvalifikátor** pole a zvolte ze seznamu zařízení, které jste připojili k před zařízení.  
  
    -   Zvolte **najít** vybrat zařízení ze seznamu zařízení v místní podsíti.  
  
3.  Zadejte typ kód, který chcete ladit v **přiřadit** pole.  
  
     Zvolte **vyberte** a pak udělejte jednu z následujících akcí:  
  
    -   Zvolte **automaticky určit typ kódu k ladění**.  
  
    -   Zvolte **ladění tyto typy kódu** a potom vyberte jeden nebo více typů ze seznamu.  
  
4.  V **dostupné procesy** vyberte odpovídající **wwahost.exe** procesu. Použití **název** sloupec k identifikaci vaší aplikace.  
  
5.  Zvolte **připojit**.  
  
 Visual Studio připojí ladicí program k procesu. Provádění pokračuje, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k neošetřené výjimce nebo ukončení aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Řízení provádění v relaci ladění (JavaScript)](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md)   
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)   
 [Aktivovat pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)