---
title: Spouštění aplikací pro UWP ve vzdáleném počítači | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/05/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2845057fe970299d249d580d97b557a5ed311fc0
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38795969"
---
# <a name="run-uwp-apps-on-a-remote-machine-in-visual-studio"></a>Spouštění aplikací pro UWP ve vzdáleném počítači v sadě Visual Studio
  
Ke spuštění aplikace UPW na vzdáleném počítači, je nutné připojit pomocí nástroje Remote Tools for Visual Studio. Nástroje remote tools umožňují spouštět, ladění, profilování a testovat aplikace pro UPW, která běží na jednom zařízení z druhého počítače, na kterém běží Visual Studio. Spuštění na vzdáleném zařízení může být zvláště efektivní, když počítač Visual Studio nepodporuje funkce, které jsou specifické pro aplikace UWP, jako je například dotykového ovládání, geolokační a fyzická orientace. Toto téma popisuje postupy pro konfiguraci a spuštění vzdálené relace.

V některých scénářích jsou nástroje pro vzdálenou automaticky nainstaluje při nasazení na vzdáleném zařízení.

- Pro počítače s Windows 10 Creators Update a novějších verzí nástroje pro vzdálenou se nainstaluje automaticky.
- Pro zařízení s Windows 10 Xbox, IOT a HoloLens nástroje pro vzdálenou se nainstaluje automaticky.
- Pro mobilní zařízení Windows 10, musíte být fyzicky připojení k telefonu, je nutné povolit [vývojářský režim](/windows/uwp/get-started/enable-your-device-for-development) a je nutné vybrat **zařízení** jako cíl ladění. Vzdálené nástroje nejsou požadovaná nebo podporované.

Pro počítače s Windows 10 vám pre Tvůrce aktualizace verzí systému Windows nainstalujte nástroje remote tools na vzdáleném počítači ručně předtím, než můžete ladit. Postupujte podle pokynů v tomto tématu. 
  
##  <a name="BKMK_Prerequisites"></a> Požadované součásti  
 Ladění na vzdáleném zařízení:  
  
- Vzdálené zařízení a počítače Visual Studio musí být připojeny přes síť nebo připojeny přímo pomocí kabelu USB nebo Ethernet. Ladění po Internetu není podporováno.  

- Je nutné povolit [vývojářský režim](/windows/uwp/get-started/enable-your-device-for-development). 
  
- Pro počítače s Windows 10 s verzí Windows 10 starší než Windows 10 Creators Update, je nutné [nainstalujte a spusťte součásti vzdáleného ladění](#BKMK_download).
  
##  <a name="BKMK_Security"></a> Zabezpečení  
Ve výchozím nastavení **univerzální (nešifrovaný protokol)** se používá ve Windows 10. Tento protokol by měl být používán pouze v důvěryhodných sítích. Připojení ladění je ohrožené kyberzločinci, kteří by mohl zachytit a změnit dat předávaných mezi vývojem a vzdálený počítač.
  
> [!WARNING]
>  Pokud nastavíte režim ověřování není žádné zabezpečení sítě **univerzální (nešifrovaný protokol)** nebo **žádný**. Zvolte těchto režimech pouze v případě, že jste si jisti, že není síť ohrožena škodlivými nebo nevyžádanými daty.  
  
##  <a name="BKMK_DirectConnect"></a> Jak se připojit přímo pomocí kabelu USB 

Ve Windows 10, můžete nasadit do zařízení připojená přes USB výběrem **zařízení** místo **vzdálený počítač** jako cíl nasazení (můžete to provést **standardní** nástrojů nebo na stránce vlastností ladění).

##  <a name="BKMK_ConnectVS"></a> Konfigurace projektu Visual Studio pro vzdálené ladění  
 Zadáte vzdáleného zařízení pro připojení k ve vlastnostech projektu. Postup se liší v závislosti na programovacím jazyce. Můžete zadat název sítě vzdáleného zařízení nebo můžete vybrat z **připojení ke vzdálené** dialogové okno.  
  
 ![Dialogové okno Vyberte připojení vzdáleného ladicího programu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 Dialogové okno obsahuje pouze zařízení, které jsou v místní podsíti počítače Visual Studio, která používají vzdálený ladicí program.  
  
> [!TIP]
>  Pokud máte potíže s připojením ke vzdálenému zařízení, zkuste zadat IP adresu zařízení. Pokud chcete zjistit IP adresu zařízení, otevřete okno příkazového řádku a zadejte **ipconfig**. IP adresa je uvedena jako **IPv4 adresu**.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a> Zvolte vzdáleného zařízení pro projekty jazyka C# a Visual Basic  
  
1.  V Průzkumníku řešení vyberte název projektu a klikněte na tlačítko **vlastnosti** z místní nabídky.  
  
2.  Vyberte **ladění**.  
  
3.  Zvolte **vzdálený počítač** z **cílové zařízení** seznamu.  
  
4.  Zadejte síťový název vzdáleného zařízení **vzdálený počítač** pole nebo zvolte **najít** pro výběr zařízení z **vyberte připojení vzdáleného ladicího programu** dialogové okno. 

    ![Spravovat vlastnosti projektu pro vzdálené ladění](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a> Zvolte vzdáleného zařízení pro projekty jazyka JavaScript a C++  
  
1.  V Průzkumníku řešení vyberte název projektu a klikněte na tlačítko **vlastnosti** z místní nabídky.  
  
2.  Rozbalte **vlastnosti konfigurace** uzlu a pak vyberte **ladění**.  
  
3.  Zvolte **vzdálený ladicí program** z **ladicí program ke spuštění** seznamu.  
  
4.  Zadejte síťový název vzdáleného zařízení **název počítače** pole nebo klikněte na šipku dolů v poli pro výběr ze zařízení **vyberte připojení vzdáleného ladicího programu** dialogové okno.  

    ![C&#43; &#43; vlastnosti pro vzdálené ladění projektu](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a> Stáhněte a nainstalujte nástroje remote tools (předběžné Creators Update)

Pokud používáte vám pre Tvůrce aktualizované verze Windows 10, postupujte podle těchto pokynů. V opačném případě můžete tuto část přeskočit.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a> Spustit relaci vzdáleného ladění  
 Spuštění, zastavení a procházení vzdálené ladicí relace stejným způsobem jako místní relaci. Na verze pre Tvůrce aktualizací Windows 10 Ujistěte se, že sledování vzdáleného ladění běží na vzdáleném zařízení.  
  
 Klikněte na tlačítko **spustit ladění** na **ladění** nabídce (klávesnice: F5). Projekt je znovu zkompilovat, pak nasadí do a spustit na vzdáleném zařízení. Ladicí program pozastaví provádění na zarážkách a můžete krokovat do, nad a z kódu. Zvolte **Zastavit ladění** ukončíte ladicí relaci a zavřete vzdálenou aplikaci.
  
## <a name="see-also"></a>Viz také  
 [Pokročilé možnosti vzdáleného nasazení](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [Testování aplikací pro UPW pomocí sady Visual Studio](../test/testing-store-apps-with-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)
