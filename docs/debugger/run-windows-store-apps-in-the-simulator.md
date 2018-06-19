---
title: Spuštění aplikace UWP v simulátoru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 81b69bf8-ec87-4bb6-9ad4-1fa7b7802d16
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 99881b657f6d3cb6877c7ce6d1fbf80f4eb1d731
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480658"
---
# <a name="run-uwp-apps-in-the-simulator"></a>Spuštění aplikace UWP v simulátoru
Visual Studio simulátor pro aplikace UWP je aplikace pracovní plochy, která simuluje aplikace UPW. Obvykle budete chtít ladění na místním počítači, připojeného zařízení nebo vzdáleném počítači. V některých scénářích, můžete však použít simulátoru Visual Studio k emulaci různých fyzických velikost a rozlišení obrazovky. Můžete také simulace událostí otočení a běžné touch a simulovat vlastnosti síťového připojení.
  
 Simulátor poskytuje prostředí, ve kterém můžete navrhnout, vývoj, ladění a testování aplikace UWP. Ale předtím, než můžete publikovat aplikaci Microsoft Store, byste měli otestovat vaši aplikaci ve skutečné zařízení.  
  
 Visual Studio simulátor pro aplikace UWP se nespouští v izolovaném prostředí na místním počítači. Chyby, ke kterým došlo v simulátoru, jako je například k neobnovitelné chybě systémového proto může ovlivnit celý počítač.  
  
> [!IMPORTANT]
>  Visual Studio 2015 simulátor nezahrnuje tlačítko informace o zeměpisné poloze. To je proto simulátoru Windows 10 nezahrnuje informace o zeměpisné poloze simulace.
  
##  <a name="BKMK_Set_the_simulator_as_the_target"></a> Simulátor nastavenou jako cíl  
 Ke spouštění vaší aplikace UWP v simulátoru, vyberte **simulátoru** z rozevíracího seznamu vedle položky **spustit ladění** tlačítko ladicí program **standardní** panelu nástrojů. Tato možnost je k dispozici, pouze pokud vaše aplikace **cílové platformy Min. Verze** je menší než nebo rovna operační systém na vývojovém počítači. 
  
 ![Spuštění v simulátoru](../debugger/media/vsrun_f5_simulator.png "VSRUN_F5_Simulator")  
  
##  <a name="BKMK_Choose_an_interaction_mode"></a> Vyberte režim interakci  
 Můžete vybrat následující režimy interakce  
  
-   ![Tlačítko režimu myši](../debugger/media/simulator_mousemodebtn.png "SIMULATOR_MouseModeBtn") myši režimu: Nastaví režim interakce na gesta myši. Zahrnout myši gesta kliknutí na poklikáním a drags.  
  
-   ![Tlačítko Start touch emulace](../debugger/media/simulator_starttouchemulationbtn.png "SIMULATOR_StartTouchEmulationBtn") emulace touch Start: Nastaví režim interakce touch gesta jednoho prstu. Jedním prstem události zahrnují klepnutím přetahování a k načtení.  
  
     ![Cíl jedním prstem simulátoru](../debugger/media/simulator_onefinger.png "SIMULATOR_OneFinger") jedním cílem ikona označuje umístění události v simulátoru. Umístěte ukazatel pomocí myši.  
  
     ![Cíl touch jedním prstem](../debugger/media/simulator_onefingerengaged.png "SIMULATOR_OneFingerEngaged") stiskněte levé tlačítko aktivovat režimu dotykového ovládání. Například klikněte na tlačítko pro simulaci klepněte na nebo stiskněte a podržte tlačítko a přetáhněte nebo prstem.  
  
## <a name="pinch-and-zoom"></a>Prohnutí a přiblížení  
 Nastaví režim interakce prohnutí a přiblížení gesta dvě prstů.  
  
-   ![Cíl prstem Siimulator dva](../debugger/media/simulator_twofinger.png "SIMULATOR_TwoFinger")  
  
     Ikona dvojité cíl označuje umístění dvěma prsty na obrazovce zařízení.  
  
    -   Najeďte myší na pozici ikony přes objekt na obrazovce zařízení.  
  
    -   Otočte kolečka myši dopředu, chcete-li změnit simulované vzdálenost dvěma prsty před prohnutí nebo zvětšení nebo dozadu.  
  
-   -   ![Prohnutí, Lupa a otočení cíle](../debugger/media/simulator_twofingerengaged.png "SIMULATOR_TwoFingerEngaged")  
  
         Stiskněte tlačítko levé a otočit wheel zpětné (směrem k) Chcete-li zvětšit (roztahováním).  
  
    -   Stiskněte tlačítko levé a otočit kolečka myši směrem vpřed (od sebe) k oddálení (Lupa).  
  
## <a name="object-rotation"></a>Otočení objektu  
 **Touch emulace otočit** tlačítko nastaví režim interakce na otočení gesta pomocí dvou prstů.  
  
-   -   Najeďte myší na pozici ikony přes objekt na obrazovce zařízení.  
  
    -   Otočte kolečka myši dopředu změnit simulované orientaci dvěma prsty než otočit objekt nebo dozadu.  
  
-   -   Stiskněte tlačítko levé a otočit zpětné (směrem k) wheel otočení objektu proti směru hodinových ručiček. Jako otočení kolečka myši jednu z ikon dvě cílové otočí kolem dalších udávajících relativní velikost je oběh.  
  
    -   Stiskněte tlačítko levé a otočit kolečka myši směrem vpřed (od sebe) otočení objektu po směru hodinových ručiček.  
  
##  <a name="BKMK_Enable_or_disable_Always_on_top_mode"></a> Povolit nebo zakázat vždy na začátek režimu  
 Můžete nastavit okno simulátoru a vždy je nutné popředí. **Přepnout nejhornější okno** tlačítko povolí nebo zakáže **vždy nahoře** režimu okna simulátoru.  
  
##  <a name="BKMK_Change_the_device_orientation"></a> Změna orientace zařízení  
 Orientace zařízení mezi na výšku a šířku můžete přepnout otočením simulátoru 90 stupňů vede libovolným směrem.  
  
> [!NOTE]
>  Simulátor nerespektuje [DisplayProperties.AutoRotationPreferences](http://go.microsoft.com/fwlink/?LinkId=249460) vlastnosti projektu. Například, pokud projekt nastaví orientaci na `Landscape`a pak otočit simulátoru k orientaci na výšku, bitovou kopii zobrazení simulátoru také otáčet, který se po změně velikosti. Vyzkoušejte toto nastavení na skutečné zařízení.  
  
> [!NOTE]
>  Při otočení simulátoru tak, aby jeden okraj simulátoru je větší než, které se zobrazí na obrazovce, simulátoru se automaticky přizpůsobí v rámci obrazovky. Simulátor není původní velikost ke změně velikosti, pokud znovu otočit.  
  
##  <a name="BKMK_Change_the_simulated_screen_size_and_resolution"></a> Změnit velikost simulované obrazovky a řešení  
 Chcete-li změnit velikost simulované obrazovky a řešení, vyberte **změnit řešení** tlačítko na paletě a ze seznamu vyberte novou velikost a řešení.  
  
 Velikost obrazovky a řešení jsou uvedeny jako *palce šířka obrazovky, pixelů šířka a výška pixelů*. Všimněte si, simulated velikosti obrazovky a rozlišení. Souřadnice umístění v simulátoru jsou převedeny na souřadnice velikost vybrané zařízení a řešení.  
  
> [!NOTE]
>  Škálovat verzích rastrové obrázky můžete uložit ve vaší aplikaci a systém Windows načte správné bitové kopie pro aktuální měřítka. Další informace najdete v tématu [návrhu a uživatelského rozhraní ÚVOD](/windows/uwp/layout/design-and-ui-intro). Nicméně pokud změníte simulátoru řešení, které systém Windows vybere jinou bitovou kopii podle řešení, budete muset zastavit a restartovat relaci ladění zobrazíte novou bitovou kopii.  
  
##  <a name="BKMK_Capture_a_screenshot_of_your_app_for_submission_to_the_Microsoft_Store"></a> Vytvoření snímku obrazovky aplikace pro odeslání Microsoft Store  
 Při odesílání aplikace do Microsoft Store, musíte zahrnout snímky obrazovky aplikace.  
  
> [!NOTE]
>  Na snímku obrazovky je uložen na aktuální řešení simulátoru. Chcete-li změnit na řešení, vyberte **změnit řešení** tlačítko.  
  
-   Chcete-li vytvořit snímky obrazovky aplikace z simulátoru, zvolte **snímku obrazovky do schránky** tlačítko.  
  
-   Pokud chcete nastavit umístění, kde se nachází snímky obrazovky, vyberte **– snímek obrazovky nastavení** tlačítko a vyberte umístění v místní nabídce.  
  
     ![Snímek obrazovky nastavení kontextovou nabídku](../debugger/media/simulator_screenshotsettingscntxmnu.png "SIMULATOR_ScreenShotSettingsCntxMnu")  
  
##  <a name="BKMK_Simulate_network_connection_properties"></a> Simulovat vlastnosti síťového připojení  
 Může pomoci spravovat údržbu povědomí o síťové připojení náklady nebo data plán změny stavu a povolením vaši aplikaci tyto informace používat účtovány dodatečné poplatky pro roaming nebo vyšší než náklady na měřeném připojení k síti uživatelé vaší aplikace Zadaná data limit přenosu. [Windows.Networking.Connectivity](/uwp/api/windows.networking.connectivity) rozhraní API umožňuje reagovat na [NetworkStatusChanged](/uwp/api/windows.networking.connectivity.networkinformation) a [TriggerType](/uwp/api/windows.applicationmodel.background.systemtrigger) události, které přihlásit. V tématu [rychlý start: Správa sítí s měřením dat náklady omezení](http://msdn.microsoft.com/library/windows/apps/Hh750310.aspx).  
  
 K ladění a testování ohledem na náklady kódu sítě, můžete simulátoru napodobovat vlastnosti sítě, které jsou k dispozici prostřednictvím [ConnectionProfile](/uwp/api/windows.networking.connectivity.connectionprofile) objekt vrácený [GetInternetConnectionProfile](/uwp/api/windows.networking.connectivity.networkinformation).
  
 Pro simulaci vlastnosti sítě:  
  
1.  Na panelu nástrojů simulátoru zvolte **změnit vlastnosti sítě** tlačítko.  
  
2.  Na **nastavit vlastnosti sítě** dialogové okno, vyberte **použití simulated vlastnosti sítě**.  
  
     Zrušte zaškrtnutí políčka odebrat simulace a vrátíte se na vlastnosti síťových rozhraní aktuálně připojené.  
  
3.  Zadejte **název profilu** pro simulované síti. Doporučujeme použít jedinečný název, který můžete použít k identifikaci simulace v [ProfileName](/uwp/api/windows.networking.connectivity.connectionprofile) vlastnost [ConnectionProfile](/uwp/api/windows.networking.connectivity.connectionprofile) objektu.  
  
4.  Vyberte [NetworkCostType](/uwp/api/windows.networking.connectivity.networkcosttype) hodnotu pro profil z **náklady na typ sítě** seznamu.  
  
5.  Z **Data Limit stav příznak** seznamu, můžete nastavit [ApproachingDataLimit](/uwp/api/windows.networking.connectivity.connectioncost) vlastnost nebo [OverDataLimit](/uwp/api/windows.networking.connectivity.connectioncost) vlastnost na hodnotu true, nebo můžete zvolit  **V části Limit dat** nastavit obě hodnoty na hodnotu false.  
  
6.  Z **Roaming stavu** seznamu, nastavte [Roaming](/uwp/api/windows.networking.connectivity.connectioncost) vlastnost.  
  
7.  Zvolte **nastavit vlastnosti** k simulaci vlastnosti sítě pomocí spouštění popředí [NetworkStatusChanged](/uwp/api/windows.networking.connectivity.networkinformation) události a na pozadí [SystemTrigger](/uwp/api/windows.applicationmodel.background.systemtrigger) typu  **NetworkStateChange**.  
  
 **Další informace o správě připojení k síti**  
  
 [Rychlý úvod: Správa měření podle objemu omezení náklady na síť](http://msdn.microsoft.com/library/windows/apps/Hh750310.aspx)  
  
 [Ukázka informace o síti](http://code.msdn.microsoft.com/windowsapps/Network-Information-Sample-63aaa201)  
  
 [Analýza spotřeby energie](../profiling/analyze-energy-use-in-store-apps.md)  
  
 [Windows.Networking.Connectivity](/uwp/api/windows.networking.connectivity)  
  
 [Způsob reakce na události systému s úkoly na pozadí](http://msdn.microsoft.com/en-us/f7c86e86-a7ae-4abb-a923-76b03337a80a)  
  
 [Jak aktivovat pozastavení, obnovení a události na pozadí v aplikacích pro UWP](http://msdn.microsoft.com/library/windows/apps/hh974425.aspx)  
  
##  <a name="BKMK_Navigate_the_simulator_with_the_keyboard"></a> Přejděte simulátoru pomocí klávesnice  
 Můžete přejít simulátoru nástrojů stisknutím klávesy **kombinaci kláves CTRL + ALT + Šipka nahoru** přejděte fokus z okna simulátoru na panelu nástrojů simulátoru. Použití **šipka nahoru** a **šipka dolů** přecházet mezi tlačítka panelu nástrojů.  
  
 Simulátor můžete vypnout stisknutím **CTRL + ALT + F4**.  
  
## <a name="see-also"></a>Viz také  
 [Spuštění aplikace ze sady Visual Studio](../debugger/run-store-apps-from-visual-studio.md)