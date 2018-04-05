---
title: Další informace o mobilní vývoj s Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.technology: vs-ide-mobile
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 30d2bf7dbcacec6490bf36584b62c200bfab0da8
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/05/2018
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Další informace o mobilní vývoj pomocí Xamarinu

Tento článek obsahuje seznam několik přehledy, které vám může pomoct pochopit, vývoj mobilních aplikací pro víc platforem pomocí Xamarinu. Pokud jste ještě nenainstalovali, Visual Studio a Xamarin, spusťte [nastavení a instalaci](../cross-platform/setup-and-install.md) proces nejprve, pak se vraťte sem práci prostřednictvím těchto prostředků, zatímco instalační programy běží.  
  
> [!NOTE]
> Pokud není uvedeno jinak, původně můžete číst jenom tyto stránky, které jsou propojené přímo z tohoto místa a není jiné stránky. Proces instalace spuštěné po dokončení tohoto seznamu, klidně přejít zpět a prozkoumat další témata.  
>   
> Také klidně si projděte si témata označena "Essentials" a vraťte se na témata "Podrobnější prohlídku" později.  
  
## <a name="essentials-introduction-to-xamarin"></a>Essentials: Úvod do Xamarin  

*10-20 minut*  
  
1.  [Mobilní aplikace v sadě Visual Studio s Xamarinem](https://www.visualstudio.com/xamarin/) (visualstudio.com) poskytuje krátké rundown primární vlastností Xamarin.  
  
2.  [Vytváření napříč platformami mobilních aplikací pomocí jazyka C# a Visual Studio](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (Channel9, 15m16s) s Xamarin věrného, James Montemagno. První tři minuty jsou přehled Xamarin, za nímž následuje ukázky kódu.  
  
## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>Essentials: Přehled Visual Studio a Xamarin prostředí  

*5-15 minut*  
  
-   Můžete to udělat většinu práce na počítači s Windows nainstalované s Visual Studio a Xamarin. V tomto počítači můžete přímo vytvářet Windows a aplikací pro Android a spuštění a ladění je na ploše, zařízení nebo emulátorů. Můžete taky vzdáleně sestavit, spuštění a ladění aplikací pro iOS prostřednictvím Mac. Visual Studio v počítači s Windows můžete také připojit k návrháře storyboard iOS a simulátoru iOS.  
  
-   Mac s Xcode a Visual Studio pro Mac, které jsou nainstalované slouží jako hostitele sestavení, podepisování hostitele a prostředí runtime pro aplikace iOS. Delegáti iOS počítače Windows sestavení do této Mac. Aplikace běží na simulátoru iOS na Mac, nebo přímo na připojené zařízení připojené k Mac. Můžete pracovat s aplikací na Mac, ale chování zkušenosti s laděním v sadě Visual Studio.
  
Tyto relace jsou zobrazené níže.  
  
![Vztah mezi Windows a Mac dev počítačů v prostředí Xamarin](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin další 1")  

> [!NOTE]
> Windows Phone se zobrazí v tomto diagramu pro účely úplnost. Při použití platformy Xamarin, doporučená možnost sdílení kódu je rozhraní .NET 2.0 standardní knihovny, která není kompatibilní s zařízení Windows Phone nebo Windows 10 Mobile. 

Další informace o práci s aplikacemi pro iOS na [Úvod do Xamarin.iOS pro sadu Visual Studio](/xamarin/ios/get-started/installation/windows/introduction-to-xamarin-ios-for-visual-studio/).
  
## <a name="essentials-how-projects-are-structured"></a>Essentials: Jak projekty jsou strukturovaná  

*10 až 30 minut*  
  
1.  [Sdílení kódu možnosti](/xamarin/cross-platform/app-fundamentals/code-sharing/). Pro nové aplikace měli byste použít knihovnu .NET Standard sdílet kódu. Většina obchodní logiky kód se bude nacházet v knihovně .NET Standard, včetně přístupu k databázím, volání rozhraní REST API a volání přenosné součástí Xamarin. (Viz [podrobnější prohlídku: součástí Xamarin](#components) na konci tohoto článku). Společný kód uživatelského rozhraní, které jsou napsané pomocí Xamarin.Forms se nachází taky v rozhraní .NET standardní knihovna.  
  
2.  (Volitelné) [Případová studie: Tasky](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/case-study-tasky/) popisuje některé z osvědčených postupů pro návrh a struktura plně funkční aplikace, jako je například vytváření struktury projekt pomocí sdíleného kód, který odděluje data, přístup k datům a obchodní vrstvy.  
  
## <a name="essentials-native-and-xamarinforms-ui-layers"></a>Essentials: nativní a vrstvy Xamarin.Forms uživatelského rozhraní  

*10 40 minut*  
  
Xamarin nabízí dva způsoby, jak k vytváření kvalitních aplikací: nativní Xamarin a Xamarin.Forms.  
  
Pomocí Xamarin Native zápisu samostatné kód uživatelského rozhraní pro každou cílovou platformu: iOS, Android a Windows.  S tímto přístupem budete mít přímý přístup k rozhraní API specifické pro platformu návrhu vlastní uživatelské rozhraní na každou platformu.  Máte také plný přístup k nativní designer a ovládací prvky pro každou platformu, které pomáhají při vytváření příslušných uživatelského rozhraní.  
  
Xamarin.Forms poskytuje sadu rozhraní API, který umožňuje zapisovat sdílené vrstvy uživatelského rozhraní pro všechny platformy .NET standardní knihovny zobecněný.  Xamarin.Forms vykresluje nativní ovládací prvky na jednotlivých platformách cíl zajistit přirozený vzhled a chování.  Místo pomocí návrháře, vytvořit uživatelské rozhraní pomocí jazyka C# a XAML.  

Většina vývojářů používají Xamarin.Forms. Toto je doporučená trasy pro vývojáře pro Xamarin nové. Xamarin nativní přístup je složitější a vyžaduje podrobnější informace o cílové platformy.
  
Není nutné rozhodnout, jaký přístup provést předem; aplikace může být implementovaná pomocí kombinace nativní Xamarin a Xamarin.Forms:  
  
-   Xamarin.Forms použijte k vytvoření obrazovky pro obecné účely. Tyto zadejte podobné uživatelské rozhraní a možnosti různých platformách, jako je například přihlášení, obraťte se na formulářů a výsledky hledání.  
  
-   Použijte celou řadu možností přizpůsobení v Xamarin.Forms upravit uživatelského rozhraní na základě na platformu. Zahrnuje nejjednodušší možnost přizpůsobení `OnPlatform` rozhraní API. Můžete také vytvořit vlastní zobrazení, rozšířit existující nástroji pro vykreslování a vytvořit vlastní nástroji pro vykreslování.  
  
-   V případě potřeby použijte k vytvoření obrazovky, které používají jedinečné funkce uživatelského rozhraní pro každou platformu nativní Xamarin. Jedním z příkladů je k obrazovce, která používá manipulaci zachycení a bitové kopie nativní fotoaparát.  
  
Obecně byste měli začít s řešením Xamarin.Forms kód uživatelského rozhraní sdílení napříč platformami. Pomocí možnosti přizpůsobení proveďte úpravy specifické pro platformu. Pokud potřebujete obrazovky zcela specifických pro platformy, můžete přidat ty jednotlivě pomocí nativní Xamarin.  
  
Další informace:  
  
1.  [Xamarin.Forms](/xamarin/xamarin-forms/) poskytuje stručný přehled a výhody a nevýhody Xamarin.Forms oproti nativní vrstvy uživatelského rozhraní (to znamená, Xamarin.iOS a Xamarin.Android).  
  
2.  První tři minuty James Montemagno video [Xamarin.Forms: nativní aplikace pro iOS, Android a Windows aplikací pomocí jazyka C# & XAML](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704) (Channel9, 13m3s) poskytuje další přehled a sledování pro ukázky můžete pokračovat.  
  
3.  (Volitelné) [Úvod k platformě Xamarin.Forms](/xamarin/xamarin-forms/get-started/introduction-to-xamarin-forms/)  
  
4.  (Volitelné) Příklady použití `OnPlatform` k přizpůsobení v [třídu zařízení](/xamarin/xamarin-forms/platform/device/) dokumentace
  
5.  (Volitelné) [Napříč platformami - sdílenou složku uživatelského rozhraní kód napříč mobilní platformy, s Xamarin.Forms](https://msdn.microsoft.com/magazine/dn904669.aspx) podle Jason Smith (Časopis MSDN) jsou podrobněji popsány dále přizpůsobení různé možnosti v rámci Xamarin.Forms, pro které jsou popsané podrobnosti na [ Vlastní nástroji pro vykreslování](/xamarin/xamarin-forms/app-fundamentals/custom-renderer/).  
  
## <a name="deeper-dive-debugging-with-emulators"></a>Podrobnější prohlídku: Ladění pomocí emulátorů  

*10 až 15 minut*  
  
K ladění aplikací pro různé platformy bez nutnosti použití fyzického zařízení, je potřeba použít emulátorů popsané tady:  
  
### <a name="microsofts-android-emulator"></a>Emulátoru Android od Microsoftu 

Je doporučeno používat společnosti Microsoft [Visual Studio Emulator for Android](~/cross-platform/visual-studio-emulator-for-android.md), který je nainstalován pomocí sady Visual Studio.  [Visual Studio Emulator for Android](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) video (Channel9, 5m55s) nabízí přehled a ukázka.  
  
### <a name="apples-ios-simulator"></a>Simulátoru iOS společnosti Apple

Další informace, přečtěte si [Začínáme s simulátoru iOS](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com).  
  
### <a name="microsofts-windows-phone-emulator"></a>Emulátor Windows Phone společnosti Microsoft.

Další informace, přečtěte si [Test pomocí emulátoru Microsoft pro Windows 10 Mobile](/windows-uwp/windows-apps-src/debug-test-perf/test-with-the-emulator/).  
  
<a name="components" /> 

## <a name="deeper-dive-xamarin-components"></a>Podrobnější prohlídku: Součástí Xamarin  

*10 minut*  
  
Mnoho rozšířené možnosti jsou k dispozici pro aplikace Xamarin prostřednictvím součástí Xamarin. Můžete najít plné katalogové k dispozici ke stažení na [ http://components.xamarin.com/ ](http://components.xamarin.com/), která obsahuje součásti pro další ovládací prvky uživatelského rozhraní, ověřování, různých cloudových služeb, jako je Microsoft Azure a mnoho dalšího.