---
title: Další informace o vývoji mobilních aplikací s využitím kódu Xamarin | Dokumentace Microsoftu
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.prod: xamarin
ms.technology: xamarin-tools
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 98371b648dc7fe18315904d4759b55701a07f7b1
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251676"
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Informace o vývoji pro mobilní zařízení v Xamarinu

Tento článek uvádí několik přehledy, které vám pomůžou pochopit, vývoj multiplatformních mobilních aplikací s využitím kódu Xamarin. Pokud jste ještě nenainstalovali aplikaci Visual Studio a Xamarin, spusťte [nastavení a instalaci](../cross-platform/setup-and-install.md) procesu nejprve, pak se sem vraťte pro seznámení se základními tyto prostředky jsou spuštěné instalační programy.

> [!NOTE]
> Pokud není uvedeno jinak, původně můžete chtít číst pouze stránky, propojit přímo ze zde a ne pobočkách stránky. Pokud po dokončení tohoto seznamu je stále spuštěn proces instalace, můžete přejít zpět a prozkoumat další témata.
>
> Také neváhejte tématech označený "Essentials" a vraťte se na témata "Dozvědět více o" později.

## <a name="essentials-introduction-to-xamarin"></a>Základy: Úvod do Xamarin

*10-20 minut*

1.  [Mobilní aplikace v sadě Visual Studio s Xamarinem](https://visualstudio.microsoft.com/xamarin/) (visualstudio.com) poskytuje krátký přehled primární charakteristiky Xamarin.

2.  [Vytváření multiplatformních mobilních aplikací v C# a Visual Studio](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (Channel9, 15m16s) s Xamarin evangelista, James Montemagno. První tři minuty se přehled Xamarin, za nímž následuje ukázky kódu.

## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>Essentials: Přehled produktu prostředí sady Visual Studio a Xamarin

*5 – 15 minutách*

-   Budete provádět většinu práce v počítači Windows nainstalované s Visual Studio a Xamarin. V tomto počítači přímo sestavení Windows a aplikace pro Android a spouštění a ladění je na ploše, zařízení nebo emulátorů. Můžete také vzdáleně sestavení, spouštět a ladit aplikace pro iOS pomocí macu Visual Studio v počítači Windows můžete také připojit k iOS designer scénáře a simulátoru iOS.

-   Mac s Xcode a sadou Visual Studio pro Mac nainstalovat slouží jako hostitel sestavovací, podpisové hostitele a běhové prostředí pro aplikace pro iOS. Sestavení iOS delegáti počítače Windows na tomto počítači Mac. Aplikace bude spuštěna na simulátoru iOS na Macu nebo přímo na připojené zařízení připojená k počítači Mac. Můžete pracovat s aplikací na počítači Mac, ale chování ladicího prostředí sady Visual Studio.

Tyto relace jsou zobrazené níž.

![Vztah mezi Windows a Mac dev počítačů v prostředí Xamarin](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin další 1")

> [!NOTE]
> Windows Phone je ukazuje tento diagram pro účely úplnost. Při použití platformy Xamarin, je doporučená možnost sdílení kódu knihovny .NET Standard 2.0, který není kompatibilní s zařízení Windows Phone nebo Windows 10 Mobile.

Další informace o práci s aplikacemi pro iOS na [Úvod k Xamarin.iosu pro Visual Studio](/xamarin/ios/get-started/installation/windows/introduction-to-xamarin-ios-for-visual-studio/).

## <a name="essentials-how-projects-are-structured"></a>Základy: Jak projekty jsou strukturované

*10 – 30 minut*

1.  [Sdílejte kód – možnosti](/xamarin/cross-platform/app-fundamentals/code-sharing/). Pro nové aplikace používejte ke sdílení kódu knihovny .NET Standard. Většina kódu obchodní logiky se bude nacházet v knihovně .NET Standard, včetně přístupu k databázím, volání rozhraní REST API a volání přenosné komponent Xamarin. (Viz [dozvědět více o: komponenty Xamarin](#components) na konci tohoto článku). Společný kód uživatelského rozhraní napsané pomocí Xamarin.Forms se také nachází v knihovně .NET Standard.

2.  (Volitelné) [Případová studie: Tasky](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/case-study-tasky/) popisuje některé osvědčené postupy pro návrh a struktura plně funkčních aplikací, jako je například vytváření struktury projektu se sdíleným kódem, který odděluje dat, přístup k datům a obchodní vrstvy.

## <a name="essentials-native-and-xamarinforms-ui-layers"></a>Essentials: nativní a vrstvy uživatelského rozhraní Xamarin.Forms

*10-40 minut*

Xamarin poskytuje dva způsoby, jak vytvářet skvělé aplikace: nativní Xamarin a Xamarin.Forms.

S nativními Xamarin napíšete samostatného kódu uživatelského rozhraní pro každou cílovou platformu: iOS, Android a Windows.  S tímto přístupem nemají přímý přístup k rozhraním API specifické pro platformu pro návrh přizpůsobené uživatelské rozhraní na jednu platformu.  Máte také úplný přístup k nativní návrháře a ovládací prvky pro jednotlivé platformy, abychom vám pomohli s vytváření příslušných uživatelského rozhraní.

Xamarin.Forms poskytuje generalizovaný sadu rozhraní API, který umožňuje zapisovat do knihovny .NET Standard sdílené vrstvě uživatelského rozhraní pro všechny platformy.  Xamarin.Forms vykresluje nativní ovládací prvky na jednotlivých platformách target k poskytování přirozený vzhled a chování.  Místo použití návrháře, vytvoříte uživatelské rozhraní pomocí jazyka C# a XAML.

Většina vývojářů používá Xamarin.Forms. Toto je doporučená trasy pro vývojáře v xamarinu nové. Xamarin nativní přístup je složitější a vyžaduje podrobnější informace o cílové platformy.

Není nutné se rozhodnout, jaký přístup se ještě před zahájením; aplikace je možné implementovat pomocí kombinace nativní Xamarin a Xamarin.Forms:

-   Vytvoření obrazovky pro obecné účely pomocí Xamarin.Forms. To poskytuje podobné uživatelské rozhraní a funkce na platformách, jako je například přihlašovací údaje, obraťte se na formulářů a výsledky hledání.

-   Úprava uživatelského rozhraní na základě podle platformy pomocí širokou škálu možností vlastního nastavení v Xamarin.Forms. Nejjednodušší možnost přizpůsobení zahrnuje `OnPlatform` rozhraní API. Můžete také vytvořit vlastní zobrazení, rozšířit existující renderery a vytvořit vlastní renderery.

-   V případě potřeby použijte k vytvoření obrazovek, které používají jedinečné funkce uživatelského rozhraní pro každou platformu Xamarin nativní. Jedním z příkladů je obrazovku, která využívá nativní fotoaparátu manipulaci zachycení a image.

Obecně by měl začínat řešení Xamarin.Forms nastavení uživatelské rozhraní sdílení kódu mezi platformami. Proveďte úpravy pro konkrétní platformu s využitím možností přizpůsobení. Pokud budete potřebovat obrazovky zcela specifické pro platformu, můžete přidat ty samostatně pomocí nativní Xamarin.

Další informace:

1.  [Xamarin.Forms](/xamarin/xamarin-forms/) poskytuje stručný přehled a výhody a nevýhody Xamarin.Forms oproti nativní vrstvy uživatelského rozhraní (to znamená, Xamarin.iOS a Xamarin.Android).

2.  První tři minuty James Montemagno video [Xamarin.Forms: nativní aplikace pro iOS, Android a Windows aplikací pomocí C# a XAML](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704) (Channel9, 13m3s) poskytuje další přehled a můžete pokračovat ve sledování pro ukázky.

3.  (Volitelné) [Úvod do Xamarin.Forms](/xamarin/xamarin-forms/get-started/introduction-to-xamarin-forms/)

4.  (Volitelné) Podívejte se na příklady použití `OnPlatform` pro přizpůsobení v [třídu zařízení](/xamarin/xamarin-forms/platform/device/) dokumentace

5.  (Volitelné) [Různé platformy – kód uživatelského rozhraní sdílené složky různých mobilních platformách pomocí Xamarin.Forms](https://msdn.microsoft.com/magazine/dn904669.aspx) podle Jason Smith (Zpravodaj MSDN Magazine) jsou podrobněji popsány dále různé možnosti přizpůsobení možností v Xamarin.Forms, pro které jsou zahrnuty podrobnosti na [ Vlastní Renderery](/xamarin/xamarin-forms/app-fundamentals/custom-renderer/).

## <a name="deeper-dive-debugging-with-emulators"></a>Dozvědět více o: ladění pomocí emulátorů

*10 až 15 minut*

Chcete-li ladit aplikace pro víc platforem bez nutnosti použít fyzické zařízení, budete muset použít emulátory popsané tady:

### <a name="microsofts-android-emulator"></a>Emulátoru Androidu od Microsoftu

Doporučuje se, že používáte společnosti Microsoft [emulátor Visual Studia pro Android](visual-studio-emulator-for-android.md), která se instaluje s aplikací Visual Studio.  [Emulátor Visual Studia pro Android](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) video (webu Channel 9, 5m55s) poskytuje přehled a ukázka.

### <a name="apples-ios-simulator"></a>Simulátor Iosu společnosti Apple

Další informace najdete v článku [začít pracovat se simulátorem Iosu](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com).

### <a name="microsofts-windows-phone-emulator"></a>Emulátor Windows Phone od Microsoftu

Další informace najdete v článku [testování s emulátorem Microsoft Windows 10 Mobile](/windows/uwp/debug-test-perf/test-with-the-emulator).

<a name="components" />

## <a name="deeper-dive-xamarin-components"></a>Dozvědět více o: komponenty Xamarin

*10 minut*

Mnoho rozšířené možnosti jsou k dispozici pro aplikace Xamarin pomocí komponenty Xamarin. Můžete najít úplném katalogu, které jsou k dispozici ke stažení na [ http://components.xamarin.com/ ](http://components.xamarin.com/), která obsahuje součásti pro další ovládací prvky uživatelského rozhraní, ověřování, různých cloudových služeb, jako je například Microsoft Azure a spoustu dalších věcí.