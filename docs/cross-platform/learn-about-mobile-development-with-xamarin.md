---
title: "Další informace o mobilní vývoj s Xamarin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.technology: vs-ide-mobile
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 6dcfd6be29d8ba978605301412f7ee918deda8f2
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Další informace o mobilní vývoj pomocí Xamarinu

Toto téma vás přesměruje na přehled materiál, který vám pomůže pochopit vývoj mobilních aplikací pro víc platforem pomocí Xamarinu. Pokud jste ještě nenainstalovali, Visual Studio a Xamarin, spusťte [nastavení a instalaci](../cross-platform/setup-and-install.md) proces nejprve, pak se vraťte sem práci prostřednictvím těchto prostředků, zatímco instalační programy běží.  
  
> [!NOTE]
> Pokud není uvedeno jinak, doporučujeme nejdřív čtení jen ty stránky propojené s přímo tady a ne jiné stránky. Proces instalace spuštěné po dokončení tohoto seznamu, klidně přejít zpět a prozkoumat další témata.  
>   
> Také klidně si projděte si témata označena "Essentials" a vraťte se na témata "Podrobnější prohlídku" později.  
  
## <a name="essentials-introduction-to-xamarin"></a>Essentials: Úvod do Xamarin  

*10-20 minut*  
  
1.  [Mobilní aplikace v sadě Visual Studio s Xamarinem](https://www.visualstudio.com/explore/xamarin-vs) (visualstudio.com) poskytuje velmi krátké rundown primární vlastností Xamarin.  
  
2.  [Vytváření napříč platformami mobilních aplikací pomocí jazyka C# a Visual Studio](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (Channel9, 15m16s) s Xamarin věrného, James Montemagno. První tři minuty jsou přehled Xamarin, za nímž následuje ukázky kódu.  
  
## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>Essentials: Přehled Visual Studio a Xamarin prostředí  

*5-15 minut*  
  
-   Počítači s Windows pomocí sady Visual Studio a Xamarin je, kde většinu práce uděláte. V tomto počítači je přímo vytvářet Windows a aplikací pro Android a spuštění a ladění je na emulátoru nebo zařízení. Můžete taky vzdáleně sestavení, spuštění a ladění aplikací pro iOS prostřednictvím Mac. Visual Studio v počítači s Windows můžete také připojit k návrháře storyboard iOS a simulátoru iOS.  
  
-   Mac s Xcode a Xamarin slouží jako sestavení nebo podepisování prostředí hostitele a modulu runtime pro aplikace iOS. Sestavení pro iOS ze sady Visual Studio v počítači s Windows jsou přeneseny na tento Mac; Při ladění aplikace pro iOS ze sady Visual Studio, spustí se v simulátoru iOS na Mac nebo přímo na připojené zařízení připojené k Mac. V takovém případě budete pracovat s aplikací nebo v těsné blízkosti Mac a máte zkušenosti s laděním v sadě Visual Studio.  
  
Tyto relace jsou znázorněné dole a další informace o práci s aplikacemi pro iOS na [Úvod do Xamarin.iOS pro sadu Visual Studio](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/introduction_to_xamarin_ios_for_visual_studio/) (xamarin.com).  
  
![Vztah mezi Windows a Mac dev počítačů v prostředí Xamarin](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin další 1")  
  
## <a name="essentials-how-projects-are-structured"></a>Essentials: Jak projekty jsou strukturovaná  

*10 až 30 minut*  
  
1.  [Sdílení kódu možnosti](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/sharing_code_options/) (xamarin.com). Doporučujeme, abyste pomocí možnosti knihovny přenosných tříd, jako je nejlepší podporuje používání pouze rozhraní .NET API, které jsou podporovány v rámci všech cílových platforem. Většina obchodní logiky kód se bude nacházet v PCL, včetně přístupu k databázím, volání rozhraní REST API a volání přenosné součástí Xamarin (najdete v části [podrobnější prohlídku: součástí Xamarin](#components) na konci tohoto tématu). Společný kód uživatelského rozhraní, které jsou napsané pomocí Xamarin.Forms, mohou být také umístěny v PCL.  
  
2.  (Volitelné) [Případová studie: Tasky](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/case_study-tasky/) (xamarin.com), popisuje některé z osvědčených postupů pro návrh a struktura aplikace plně vybavené například strukturování projektu s PCL pro sdílené kód, který odděluje data, přístup k datům a obchodní vrstvy.  
  
## <a name="essentials-native-and-xamarinforms-ui-layers"></a>Essentials: nativní a vrstvy Xamarin.Forms uživatelského rozhraní  

*10 40 minut*  
  
Nabízí dva způsoby, jak vytvářet skvělé nativní aplikace Xamarin: nativní Xamarin a Xamarin.Forms.  
  
Pomocí Xamarin Native zápisu samostatné kód uživatelského rozhraní pro každou cílovou platformu: iOS, Android a Windows.  S tímto přístupem budete mít přímý přístup k rozhraní API specifické pro platformu povolení přizpůsobené uživatelské rozhraní na každou platformu.  Máte také plný přístup k nativní designer a ovládací prvky pro každou platformu, které pomáhají při vytváření příslušných uživatelského rozhraní.  
  
Xamarin.Forms poskytuje sadu rozhraní API, který umožňuje zapisovat sdílené vrstvy uživatelského rozhraní pro všechny platformy knihovny přenosných tříd zobecněný.  Xamarin.Forms vykresluje nativní ovládací prvky na jednotlivých platformách cíl umožnit přirozený vzhled a chování.  Místo pomocí návrháře, s Xamarin.Forms, vytvořit uživatelské rozhraní pomocí jazyka C# a XAML.  
  
Není nutné rozhodnout, jaký přístup provést předem; aplikace může být implementovaná pomocí kombinace nativní Xamarin a Xamarin.Forms:  
  
-   Použití Xamarin.Forms k sestavení pro obecné účely obrazovky, které poskytují podobné uživatelského rozhraní a možnosti různých platformách, jako je například přihlášení, obraťte se na forms a výsledky hledání.  
  
-   Použijte celou řadu možností přizpůsobení v Xamarin.Forms upravit uživatelského rozhraní na základě na platformu. Ty zahrnují OnPlatform rozhraní API, které je možné z jak kódu a XAML, vytvoření vlastního zobrazení, rozšíření stávající zobrazovací jednotky a vytvoření vlastní zobrazovací jednotky.  
  
-   V případě potřeby použijte k vytvoření obrazovky, které používají jedinečné funkce uživatelského rozhraní pro každou platformu, například, k obrazovce, která používá nativní fotoaparát zachycení a bitové kopie manipulace s nativní Xamarin.  
  
Doporučujeme vždy počínaje řešení Xamarin.Forms kód uživatelského rozhraní sdílení napříč platformami a možnosti vlastního nastavení s úpravami specifické pro platformu. Pokud potřebujete obrazovky zcela specifických pro platformy, můžete přidat ty jednotlivě pomocí nativní Xamarin.  
  
Další informace:  
  
1.  [Xamarin.Forms](http://developer.xamarin.com/guides/cross-platform/xamarin-forms/) (xamarin.com) poskytuje stručný přehled a výhody a nevýhody Xamarin.Forms oproti nativní vrstvy uživatelského rozhraní (to znamená, Xamarin.iOS a Xamarin.Android).  
  
2.  První tři minuty James Montemagno video [Xamarin.Forms: nativní aplikace pro iOS, Android a Windows aplikací pomocí jazyka C# & XAML](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704) (Channel9, 13m3s) poskytuje další přehled a sledování pro ukázky můžete pokračovat.  
  
3.  (Volitelné) [Úvod do Xamarin.Forms](http://developer.xamarin.com/guides/cross-platform/xamarin-forms/getting-started/introduction-to-xamarin-forms/) (xamarin.com)  
  
4.  (Volitelné) Příklady použití OnPlatform pro přizpůsobení v [třídu zařízení](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) dokumentace (xamarin.com)  
  
5.  (Volitelné) [Napříč platformami - sdílenou složku uživatelského rozhraní kód napříč mobilní platformy, s Xamarin.Forms](https://msdn.microsoft.com/magazine/dn904669.aspx) podle Jason Smith (Časopis MSDN) jsou podrobněji popsány dále přizpůsobení různé možnosti v rámci Xamarin.Forms, pro které jsou popsané podrobnosti na [ Přizpůsobení ovládacích prvků na každou platformu](http://developer.xamarin.com/guides/xamarin-forms/custom-renderer/) (xamarin.com).  
  
## <a name="deeper-dive-debugging-with-emulators"></a>Podrobnější prohlídku: Ladění pomocí emulátorů  

*10 až 15 minut*  
  
K ladění aplikací pro různé platformy bez nutnosti použití fyzického zařízení, musíte použít následující:  
  
1.  **Emulátoru Androidu.** V závislosti na tom, kterou verzi systému Windows doporučujeme buď Microsoft Visual Studio Emulator pro Android nebo Xamarin přehrávač, které nabízí vysoký výkon a podporují celou řadu možnosti zařízení:  
  
    -   **Počítače s Windows 8 +:** důrazně doporučujeme pomocí společnosti Microsoft [Visual Studio Emulator for Android](https://www.visualstudio.com/en-us/features/msft-android-emulator-vs.aspx), který je nainstalován pomocí sady Visual Studio.  [Visual Studio Emulator for Android](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) video (Channel9, 5m55s) nabízí přehled a ukázka.  
  
    -   **Windows 7 nebo dřívější Windows nebo systémem Mac OS X**: použití [Xamarin Android Player](http://developer.xamarin.com/guides/android/getting_started/installation/android-player) (xamarin.com).  
  
2.  **Simulátoru iOS společnosti Apple.** Další informace, přečtěte si [Začínáme s simulátoru iOS](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com).  
  
3.  **Emulátor Windows Phone společnosti Microsoft.** Další informace, přečtěte si [Windows Phone emulátor pro Windows Phone 8](../debugger/run-windows-phone-apps-in-the-emulator.md).  
  
##  <a name="components"></a> Podrobnější prohlídku: Součástí Xamarin  

*10 minut*  
  
Mnoho rozšířené možnosti jsou k dispozici pro aplikace Xamarin prostřednictvím součástí Xamarin. Můžete najít plné katalogové k dispozici ke stažení na [http://components.xamarin.com/](http://components.xamarin.com/), která obsahuje součásti pro další ovládací prvky uživatelského rozhraní, ověřování, různých cloudových služeb, jako je Microsoft Azure a mnoho dalšího.