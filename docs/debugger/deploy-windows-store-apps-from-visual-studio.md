---
title: "Nasazení aplikací UWP ze sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
ms.assetid: ef3a0f36-bfc9-4ca0-aa61-18261f619bff
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 359431356bb06a04857b93e10996a2123c80f129
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="deploy-uwp-apps-from-visual-studio"></a>Nasazení aplikací UWP ze sady Visual Studio
![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Nasazení funkce sady Visual Studio vytvoří a zaregistruje aplikace UWP, které jsou vytvořené pomocí sady Visual Studio na cílovém zařízení. Přesně jak aplikace registrovaná závisí na tom cílové zařízení místní nebo vzdálené:  
  
-   Pokud jsou cílem v místním počítači v sadě Visual Studio, Visual Studio zaregistruje aplikaci ze své složky sestavení.  
  
-   Pokud jsou cílem vzdáleném zařízení, Visual Studio zkopíruje soubory potřebné ke vzdálenému počítači a zaregistruje aplikaci na daném zařízení.  
  
 Při ladění aplikace ze sady Visual Studio pomocí je automatické nasazení **spustit ladění** možnost (klávesové: F5) nebo **spustit bez ladění** možnost (klávesnice: kombinace kláves CTRL + F5). Aplikace můžete nasadit také ručně. Ruční nasazení je užitečné v následujících scénářích:  
  
-   Ad-hoc testování v místním nebo vzdáleném počítači.  
  
-   Nasazení aplikace, která spustí jiné aplikaci, kterou chcete ladit.  
  
-   Nasazení aplikace, která bude ladit, když je spuštěna jiná aplikace nebo metoda.
  
##  <a name="BKMK_How_to_deploy_a_Windows_Store_app"></a>Postup nasazení aplikace pro UPW  
 Ruční nasazení aplikace je jednoduchý proces:  
  
1.  Pokud nasazujete na vzdáleném zařízení, zadejte název nebo IP adresa zařízení, na stránce vlastností projektu projektu po spuštění aplikace. (Kroky, jak provést toto jsou uvedeny níže v tomto tématu.).  
  
2.  Na panelu nástrojů ladicího programu sady Visual Studio, vyberte cíl nasazení z rozevíracího seznamu vedle položky **spustit ladění** tlačítko.  
  
     ![Spustit v místním počítači](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")  
  
3.  Na **sestavení** nabídce zvolte **nasadit**  
  
##  <a name="BKMK_How_to_specify_a_remote_device"></a>Určení vzdáleném zařízení  

**Požadavky**  
  
Na vzdáleném zařízení Windows 10, musíte povolit [režim vývojáře](/windows/uwp/get-started/enable-your-device-for-development). Na zařízení s Windows 10 verzi Tvůrce Update nebo nástrojů pro vzdálenou jsou automaticky nainstalovány později při nasazení aplikace. Další informace najdete v tématu [ladění balíček nainstalovanou aplikaci](../debugger/debug-installed-app-package.md).

> [!NOTE]
> Na Windows 8.1 a verze pre-Creator aktualizace systému Windows 10 nástrojů pro vzdálenou Visual Studio musí být nainstalován na vzdáleném zařízení a musí být spuštěna vzdáleného ladicího programu. Na Windows 8.1 je také nutné nainstalovat licenci vývojáře.
  
Nasazení použije síťový kanál vzdáleného ladicího programu k odeslání v souborech aplikace na vzdáleném zařízení.  
  
#### <a name="to-specify-a-remote-device"></a>Chcete-li určit vzdáleném zařízení  
  
1.  Na stránce vlastností ladění spouštěný projekt zadejte název nebo IP adresa cíle vzdálené nasazení.  
  
2.  Chcete-li otevřít stránku vlastnosti ladění, zvolte projekt v Průzkumníku řešení a zvolte **vlastnosti** z místní nabídky.  
  
3.  Zvolte **ladění** uzlu v okně Vlastnosti stránky.

4. Pro **cílové zařízení**, vyberte **vzdáleného počítače**.

5. V části **vzdáleného počítače**, klikněte na tlačítko **najít**.
  
4.  Můžete zadat název nebo IP adresu vzdáleného zařízení, nebo můžete zvolit ze zařízení **vzdáleného připojení** dialogové okno.  
  
     ![Dialogové okno Vyberte připojení vzdáleného ladicího programu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
     **Vzdáleného připojení** dialogové okno zobrazí zařízení, na podsíti místní sítě a jakékoli zařízení, které jsou přímo připojené k počítači Visual Studio pomocí kabelu Ethernet.  
  
 **Určení vzdáleného zařízení na stránce projektu JavaScript nebo Visual C++**  
  
 ![C & č. 43; & č. 43; vlastnosti pro vzdálené ladění projektu](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")  
  
1.  Zvolte **vzdáleného ladicího programu** z **ladicí program ke spuštění** seznamu.  
  
2.  Zadejte název vzdáleného zařízení v síti **název počítače** pole. Nebo můžete na šipku dolů v rozevíracím seznamu vyberte zařízení, z dialogového okna Vybrat připojení vzdáleného ladicího programu.  
  
 **Určení vzdáleného zařízení na stránce projekt Visual C# a Visual Basic**  
  
 ![Spravovat vlastnosti projektu pro vzdálené ladění](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
1.  Zvolte **vzdáleného počítače** z **cílové zařízení** seznamu.  
  
2.  Zadejte název vzdáleného zařízení v síti **vzdáleného počítače** pole nebo klikněte na tlačítko **najít** vybrat ze zařízení **vyberte připojení vzdáleného ladicího programu** dialogové okno.  
  
##  <a name="BKMK_Deployment_options"></a>Možnosti nasazení  
 Můžete nastavit následující možnosti nasazení na stránce vlastností ladění spouštěný projekt.  
  
 **Povolit zpětnou smyčku sítě**  
 Z bezpečnostních důvodů [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikaci, která je nainstalovaná standardním způsobem není povolená pro volání sítě do zařízení je nainstalovaný. Ve výchozím nasazení sady Visual Studio vytvoří výjimku z tohoto pravidla pro aplikace nasazené. Tato výjimka umožňuje otestovat postupy komunikace na jednom počítači. Před odesláním v aplikaci [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)], měli byste otestovat aplikace bez výjimky.  
  
 Postup odebrání výjimky zpětné smyčky sítě z aplikace:  
  
-   Na stránce vlastností C# a VB ladění, zrušte **povolit zpětné smyčky sítě** zaškrtávací políčko.  
  
-   Na stránce vlastností JavaScript a ladění, nastavte **povolit zpětné smyčky sítě** hodnotu **ne**.  
  
 **Nelze spustit, ale ladění vlastního kódu po jeho spuštění (C# a VB) nebo spuštění aplikace (JavaScript a C++)**  
 Ke konfiguraci nasazení na automatické spuštění relace ladění při spuštění aplikace:  
  
-   Na stránce vlastností C# a VB ladění, zkontrolujte **nespouštějí, ale po jeho spuštění ladění vlastního kódu** zaškrtávací políčko.  
  
-   Na stránce vlastností JavaScript a ladění, nastavte **spustit aplikaci** hodnotu **Ano**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění balíček nainstalovanou aplikaci](../debugger/debug-installed-app-package.md).   
 [Spuštění aplikace ze sady Visual Studio](../debugger/run-store-apps-from-visual-studio.md)