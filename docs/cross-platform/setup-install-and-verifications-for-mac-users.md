---
title: "Instalační program, instalace a ověření pro uživatele Mac | Microsoft Docs"
ms.custom: 
ms.date: 04/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22725520-59ba-4f6f-80e4-097b1287a34b
ms.technology: vs-ide-mobile
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 366dd699555cd3eed637687668fc194ba00d5be4
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="setup-install-and-verifications-for-mac-users"></a>Instalační program, instalace a ověření pro uživatele Mac
Toto téma je určené výhradně pro vývojáře, kteří pracují hlavně na Macu a kteří volitelně použijte sadu Visual Studio uvnitř virtuálního počítače s Windows v Mac. Pokud jste vývojář pracující hlavně na počítači se systémem Windows a muset nastavit sekundární Mac pro cílení na iOS, přečtěte si téma hlavní [nastavení a instalaci](../cross-platform/setup-and-install.md) tématu.

 Pro práci s Xamarin na Macu, budete potřebovat následující:

-   Mac s systému macOS Sierra 10.12 nebo vyšší, s Xcode a Xamarin nainstalována.

-   Jedna z následujících konfigurací:

    -   **Pro spouštění Xamarin Studio přímo na Mac:** Xamarin Studio je Xamarin pro vývojové prostředí, který podporuje vytváření aplikace Android, iOS a Windows pomocí jazyka C#.  Získáte rychlý přehled o Xamarin Studio naleznete [Xamarin Studio přehled](https://xamarin.com/studio) (xamarin.com).

    -   **Pokud již máte Parallels nebo VMWare nakonfigurovaná v počítači Mac:** používají systém Windows Visual Studio 2017 a Xamarin uvnitř Parallels nebo VMWare.  Pomocí této konfigurace Xamarin je rozšíření nainstalované s Visual Studio, která poskytuje možnost používat sady Visual Studio jako vývojové prostředí pro vytváření aplikací Android, iOS a Windows pomocí jazyka C#.  Všimněte si, že můžete získat bezplatné předplatné Parallels 3 měsíce jako součást Visual Studio Developer Essentials Program. V tématu [Microsoft Visual Studio Dev Essentials bude zahrnovat Parallels Desktop Pro a Parallels přístup](http://blog.parallels.com/blog/2015/11/18/visual-studio-dev-essentials/) (Parallels blog).

 Toto téma obsahuje pokyny pro tyto požadavky.  Je spuštěn proces instalace, najdete v tématu [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md) ke čtení a podívejte se na pozadí nezbytné materiálů.

##  <a name="mac"></a> Instalační program MAC (Apple ID, Xcode a Xamarin)

1.  Vytvoření volné Apple ID na [Moje Apple ID](https://appleid.apple.com/) Pokud již nemáte. To je nezbytné pro instalaci a přihlášení k Xcode.

2.  Stáhněte a nainstalujte Xcode z [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/).

3.  Stáhněte a nainstalujte podle pokynů Xamarin [instalace a konfigurace Xamarin.iOS](http://developer.xamarin.com/guides/ios/getting_started/installation/mac/) (xamarin.com).

4.  Po dokončení instalace Xamarin v počítačích se systémy Windows a Mac, postupujte podle pokynů [připojení k počítači Mac pomocí XMA](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com), aby mohl pracovat s iOS a Mac ze sady Visual Studio v systému Windows počítač.

##  <a name="windows"></a> Instalační program systému Windows v Parallels (Visual Studio a Xamarin)

1.  Pomocí plochy Windows, který jste nakonfigurovali v Parallels nebo VMWare, [stáhněte a spusťte instalační program pro všechny edice Visual Studio 2017](https://www.visualstudio.com/downloads/) (Community, Professional a Enterprise). Visual Studio 2017 Community je bezplatná edice; edice Professional a Enterprise můžete použít na základě zkušební verze po dobu 30 dnů.

2.  V rámci instalačního programu, klikněte na **další možnosti** tlačítko (ikona tři řádky) _vedle_ **spusťte** zvolte **upravit**.:  
  
     ![Vyberete možnost upravit v instalaci sady Visual Studio](../cross-platform/media/cross-plat-xamarin-setup-1a.png "Cross-Plat Xamarin instalační 1")  
  
3.  Zkontrolujte následující pole:

    1.  **Mobilní a herní > pro vývoj mobilních řešení s .NET**. To také automaticky vybere různé nástroje pro Android v rámci běžných nástrojů a Software Development Kit. Tato možnost by měl aktualizovat také případné existující instalace Xamarin.  
  
         ![Vyberte možnost vývoj mobilních řešení v rámci herní a vývoj mobilních řešení pro](../cross-platform/media/cross-plat-xamarin-setup-2a.png "Cross-Plat Xamarin instalace 2")  
  
    2. (Volitelné) **Windows > vývoj pro univerzální platformu Windows**. To zahrnuje možnosti instalace emulátorů bitových kopií, které bude trvat déle, než se stáhnout; vždy můžete vrátit do instalačního programu sady Visual Studio je přidat později.  

4.  Klikněte **upravit** tlačítko a nechat spustit proces. Znovu, bude to trvat delší dobu, během které doby můžete pokračovat s pokyny pro instalaci Mac a projít [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Po dokončení instalace spusťte Visual Studio a přihlaste se pomocí účtu Microsoft po zobrazení výzvy (Toto je stejný účet, který použijete s Windows).

6.  Po dokončení instalace Xamarin v počítačích se systémy Windows a Mac, postupujte podle pokynů [připojení k počítači Mac pomocí XMA](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com), aby mohl pracovat s iOS ze sady Visual Studio.

##  <a name="verify"></a> Ověřte prostředí
 Jakmile jste dokončili instalační programy, věnujte několik minut, ověřte, zda je vše připraveno prostředí vývoj na platformě Xamarin.

### <a name="xamarin-studio"></a>Xamarin Studio
 Nejdřív zkontrolujte, zda přejdete na zadané odkazy, že máte **Xamarin Studio** vybraný v horním pravém rohu, abyste viděli správnou verzi dokumentace Xamarin:

 ![Výběr Xamarin Studio naleznete v dokumentaci správný na Xamarin.com](../cross-platform/media/crossplat-xamarin-mac-1.png "CrossPlat Xamarin Mac 1")

**Android**

1.  Ověření vytvoření projektu Android podle pokynů [vytvoření projektu Android](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Ověření v Android emulátoru prostřednictvím ladění [Android Player > integrace s Xamarin Studio dokumentaci](https://developer.xamarin.com/guides/android/getting_started/installation/android-player/#Integration_with_Xamarin_Studio) (xamarin.com).

**iOS**

1.  Ověření vytvoření projektu iOS podle pokynů [vytvoření iOS](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

2.  Ověření v simulátoru iOS prostřednictvím ladění [ladění v simulátoru dokumentaci](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) (xamarin.com).

### <a name="visual-studio"></a>Visual Studio
 Nejdřív zkontrolujte, zda přejdete na zadané odkazy, že máte **Visual Studio** vybraný v horním pravém rohu, abyste viděli správnou verzi dokumentace Xamarin:

 ![Výběr sady Visual Studio naleznete v dokumentaci správný na Xamarin.com](../cross-platform/media/crossplat-xamarin-mac-2.png "CrossPlat Xamarin Mac 2")

**Android**

1.  Ověření vytvoření projektu Android podle pokynů [vytvoření projektu Android](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Ověření návrháře Android: v projektu pro Android v Průzkumníku řešení, otevřete **prostředky > rozložení > Main.axml** souboru.

    -   Pokud se zobrazí chyba s oznámením "Nainstalované sady SDK pro Android je příliš starý.", klikněte na tlačítko **otevřete Android SDK** v tom, že zpráva a vyberte nejnovější verze sady SDK, která je k dispozici. Všimněte si, že musíte používat Visual Studio jako správce a aktualizovat sadu SDK.

3.  Ověřte, zda se můžete připojit ze sady Visual Studio do emulátoru, který je nainstalován na váš Mac.  Důsledkem je, uvidíte Xamarin Player v seznamu emulátorů, které můžete vybrat z Visual Studia pro ladění.  Chcete-li to provést, postupujte podle pokynů [připojení Visual Studio Xamarin Android přehrávači](http://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/android-player-with-visual-studio-in-vm/) (xamarin.com).

**iOS**

1.  Zkontrolujte, že počítač Mac je dostupný v síti a spárované sadou Visual Studio, jak je popsáno v [připojení k počítači Mac](https://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac) (xamarin.com).

2.  Ověření vytvoření projektu iOS podle pokynů [vytvoření iOS](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

3.  Ověření návrháře storyboard: v projektu iOS v Průzkumníku řešení otevřete **MainStoryboard.storyboard** souboru. Zde je Visual Studio hostování návrháře vzdáleně systémem Mac.

4.  Ověření, sestavování a ladění:

    1.  Klikněte pravým tlačítkem na projekt pro iOS v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.

    2.  Vyberte **iPhoneSimulator** cíle ze sestavení sady Visual Studio rozevíracího seznamu, jak je uvedeno níže. Pokud nejsou uvedeny žádné simulátorů, spusťte na počítači Mac, vyberte Xcode **Xcode -> Předvolby**a klikněte na tlačítko **Stáhnout**. V části **součásti** byste měli vidět simulátoru verze, které jsou k dispozici ke stažení. Další pokyny pro ladění naleznete na Xamarin [ladění](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) stránky (xamarin.com).

         ![Výběr iPhoneSimulator sestavení cíl](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin ověřte 5")

    3.  Vyberte cíl iPhone ze sady Visual Studio ladění rozevíracího seznamu, jak je uvedeno níže a spuštění ladicího programu stisknutím klávesy F5. Spustí se simulátoru v systému Mac, kde budete pracovat s aplikací, při ladění se stane v sadě Visual Studio.

         ![Výběr cíli ladění iPhone](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin ověřte 6")