---
title: "Spuštění aplikace UWP ve vzdáleném počítači | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
caps.latest.revision: "43"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e1b298f8088adf05992f7ebf8b5afbb743ec995
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="run-uwp-apps-on-a-remote-machine"></a>Spuštění aplikace UWP ve vzdáleném počítači
![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
Ke spuštění aplikace UPW ve vzdáleném počítači, je nutné připojit se pomocí nástrojů pro vzdálenou Visual Studio. Nástroje Remote Tools umožňují spouštět, ladit, profil a testování aplikace pro UPW, která běží na jedno zařízení z druhého počítače, který běží v sadě Visual Studio. Spuštění na vzdáleném zařízení může být zvláště efektivní, když počítač Visual Studio nepodporuje funkce, které jsou specifické pro aplikace UWP, například dotykového ovládání, geografického umístění a fyzické orientace. Toto téma popisuje postupy pro konfiguraci a spouští vzdálenou relaci.

V některých scénářích nástrojů pro vzdálenou automaticky nainstaluje, když nasadíte na vzdáleném zařízení.

- Počítače s Windows 10 systémem Creators aktualizace a novějších verzích, najdete v části [ladění balíčku aplikace nainstalována](debug-installed-app-package.md#remote). Nástroje pro vzdálenou se budou instalovat automaticky.
- Pro zařízení s Windows 10 Xbox, IOT a HoloLens, najdete v části [ladění balíčku aplikace nainstalována](debug-installed-app-package.md#remote). Nástroje pro vzdálenou se budou instalovat automaticky.
- Pro Windows Phone, musíte být fyzicky připojení k telefonu, je třeba nainstalovat [licence pro vývojáře](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) (Windows Phone 8 a 8.1), nebo povolte [režim vývojáře](/windows/uwp/get-started/enable-your-device-for-development) (Windows Mobile 10), a vy musíte Vyberte **zařízení** jako cíl ladění. Nástroje pro vzdálenou nejsou požadovaná nebo podporované.

Pro počítače s Windows 8.1 a počítače s Windows 10 pre-Creator aktualizace verzí systému Windows nainstalujte nástroje pro vzdálenou ve vzdáleném počítači ručně předtím, než můžete ladit. Postupujte podle pokynů v tomto tématu.
  
##  <a name="BKMK_Prerequisites"></a>Požadavky  
 Ladění na vzdáleném zařízení:  
  
-   Vzdálené zařízení a počítač s aplikací Visual Studio musí být připojeny přes síť nebo připojeny přímo pomocí kabelu Ethernet. Ladění po Internetu není podporováno.  

- Vzdálené zařízení musí být povolen pro vývoj.

    - Pro zařízení s Windows 8 a Windows 8.1 [licence pro vývojáře](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) musí být nainstalován na vzdáleném zařízení.
    - Pro zařízení s Windows 10, musíte povolit [režim vývojáře](/windows/uwp/get-started/enable-your-device-for-development). 
  
-   Pro počítače s Windows 10 s verzí systému Windows 10 starší než Windows 10 Creator aktualizace musíte nainstalovat a spustit komponenty vzdáleného ladění.
  
-   Musíte být správce na vzdáleném zařízení ke konfiguraci brány firewall během instalace. Musí mít uživatel přístup do vzdáleného zařízení spustit nebo se připojit k vzdáleného ladicího programu.  
  
##  <a name="BKMK_Security"></a>Zabezpečení  
 Ve výchozím nastavení vzdáleného ladicího programu používá ověřování systému Windows.  
  
> [!WARNING]
>  Můžete také spustit vzdáleného ladicího programu v režimu bez ověřování, ale tento režim se důrazně nedoporučuje. Při spuštění v tomto režimu není žádné zabezpečení sítě. Na možnost Režim bez ověřování klikněte pouze v případě, že jste si jisti, že není síť ohrožena škodlivými nebo nevyžádanými daty.  
  
##  <a name="BKMK_DirectConnect"></a>Jak se připojit přímo na vzdáleném zařízení  
 K přímému připojení ke vzdálené zařízení, připojte počítač Visual Studio k zařízení pomocí kabelu standardní sítě Ethernet. Pokud zařízení nemá k portu Ethernet, můžete se připojit k kabel USB adaptér Ethernet.  
  
## <a name="BKMK_download"></a>Stáhněte a nainstalujte nástroje pro vzdálenou

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
## <a name="BKMK_setup"></a>Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]
  
##  <a name="BKMK_ConnectVS"></a>Konfigurace projektu Visual Studia pro vzdálené ladění  
 Zadejte vzdálené zařízení pro připojení k ve vlastnostech projektu. Postup se liší v závislosti na programovací jazyk. Můžete zadat síťový název vzdáleného zařízení nebo ho můžete vybrat z dialogového okna Vybrat připojení vzdáleného ladicího programu.  
  
 ![Dialogové okno Vyberte připojení vzdáleného ladicího programu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 Dialogové okno zobrazí jenom ta zařízení, které jsou v místní podsíti počítače Visual Studio a, na kterých běží vzdáleného ladicího programu.  
  
> [!TIP]
>  Pokud máte potíže s připojením ke vzdálené zařízení, zkuste zadat IP adresu zařízení. Pokud chcete určit IP adresu zařízení, otevřete okno příkazového řádku a zadejte **ipconfig**. IP adresa je uveden jako **IPv4 adresu**.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a>Výběr vzdálené zařízení pro projekty C# a Visual Basic  
 ![Spravovat vlastnosti projektu pro vzdálené ladění](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
1.  Vyberte název projektu v Průzkumníku řešení a potom zvolte **vlastnosti** z místní nabídky.  
  
2.  Vyberte **ladění**.  
  
3.  Zvolte **vzdáleného počítače** z **cílové zařízení** seznamu.  
  
4.  Zadejte název vzdáleného zařízení v síti **vzdáleného počítače** pole nebo zvolte **najít** vybrat ze zařízení **vyberte připojení vzdáleného ladicího programu** dialogové okno.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a>Výběr vzdálené zařízení pro projekty JavaScript a C++  
 ![C & č. 43; & č. 43; vlastnosti pro vzdálené ladění projektu](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")  
  
1.  Vyberte název projektu v Průzkumníku řešení a potom zvolte **vlastnosti** z místní nabídky.  
  
2.  Rozbalte **vlastnosti konfigurace** uzel a potom vyberte **ladění**.  
  
3.  Zvolte **vzdáleného ladicího programu** z **ladicí program ke spuštění** seznamu.  
  
4.  Zadejte název vzdáleného zařízení v síti **název počítače** pole nebo zvolte na šipku dolů do pole vybrat ze zařízení **vyberte připojení vzdáleného ladicího programu** dialogové okno.  
  
##  <a name="BKMK_RunRemoteDebug"></a>Spuštění relace vzdálené ladění  
 Spuštění, zastavení a přechod na relaci vzdáleného ladění stejným způsobem jako místní relace. Než začnete, ladění, zkontrolujte, zda že je spuštěna Remote Debugging Monitor na vzdáleném zařízení.  
  
 Zvolte **spustit ladění** na **ladění** nabídky (klávesové: F5). Projekt je překompilovat, pak nasazené a spustit na vzdáleném zařízení. Ladicí program pozastaví spuštění na zarážkách a můžete krok do, přes a z vašeho kódu. Zvolte **Zastavte ladění** ukončete svou relaci ladění a zavřete vzdálené aplikace. Další informace najdete v tématu [ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Testování aplikací pro UPW pomocí sady Visual Studio](../test/testing-store-apps-with-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)