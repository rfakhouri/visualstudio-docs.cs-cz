---
title: Instalační program, instalace a ověření pro uživatele počítačů Mac | Dokumentace Microsoftu
ms.custom: ''
ms.date: 04/13/2017
ms.topic: conceptual
ms.assetid: 22725520-59ba-4f6f-80e4-097b1287a34b
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: asb3993
ms.author: amburns
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: f0c4193d68eabd5a5427629cb9a4c7a3be18db3c
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251917"
---
# <a name="setup-install-and-verifications-for-mac-users"></a>Nastavení, instalace a ověření pro uživatele počítačů Mac

Toto téma je určená pro vývojáře, kteří pracují hlavně na počítači Mac a kteří volitelně použít Visual Studio uvnitř virtuálního počítače Windows na počítači Mac. Pokud jste vývojář, pracující primárně na počítači Windows a muset nastavit sekundární Mac pro cílení na iOS, najdete v hlavním [nastavení a instalaci](../cross-platform/setup-and-install.md) tématu.

Pro práci s využitím kódu Xamarin na počítači Mac budete potřebovat následující:

-   Počítač Mac s macOS Sierra 10.12 nebo vyšší, s Xcode a Xamarin nainstalovat.

-   Jeden z následujících konfigurací:

    -   **Pro spouštění Xamarin Studio přímo na Macu:** Xamarin Studio je Xamarin vývojové prostředí, která podporuje vytváření aplikace pro Android, iOS a Windows pomocí jazyka C#.  Chcete-li získat rychlý přehled toho, Xamarin Studio, přečtěte si [Xamarin Studio – přehled](https://xamarin.com/studio) (xamarin.com).

    -   **Pokud už máte Parallels nebo VMWare nakonfigurovaná na počítači Mac:** spustit Windows s Visual Studio 2017 a Xamarin uvnitř Parallels nebo VMWare.  S touto konfigurací Xamarin je rozšíření, které se instaluje se sadou Visual Studio, která poskytuje schopnost používat Visual Studio jako vývojové prostředí pro vytváření aplikací pro Android, iOS a Windows pomocí jazyka C#.  Všimněte si, že můžete získat bezplatné předplatné Parallels 3měsíční jako součást Essentials programu sady Visual Studio pro vývojáře. Zobrazit [Microsoft Visual Studio Dev Essentials zahrne Parallels Desktop Pro a přístup k softwaru Parallels](http://blog.parallels.com/blog/2015/11/18/visual-studio-dev-essentials/) (Parallels blog).

Toto téma obsahuje pokyny, jak tyto požadavky.  Když je spuštěn proces instalace, najdete v tématu [přečtěte si víc o vývoj mobilních řešení s využitím kódu Xamarin](../cross-platform/learn-about-mobile-development-with-xamarin.md) ke čtení a podívejte se na materiál nezbytné pozadí.

##  <a name="mac"></a> Nastavení MAC (Apple ID, Xcode a Xamarin)

1.  Vytvořit bezplatný Apple ID na [Apple ID, které Moje](https://appleid.apple.com/) Pokud již nemáte. To je nezbytné pro instalaci a přihlášení do Xcode.

2.  Stáhněte a nainstalujte Xcode z [ https://developer.apple.com/xcode/ ](https://developer.apple.com/xcode/).

3.  Stáhněte si a nainstalujte si Xamarin, postupujte podle pokynů [nainstalovat a nakonfigurovat Xamarin.iOS](http://developer.xamarin.com/guides/ios/getting_started/installation/mac/) (xamarin.com).

4.  Po dokončení instalace Xamarinu na počítače s Windows i Mac, postupujte podle pokynů [připojit se k počítači Mac pomocí XMA](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com), což umožní pracovat s iOS a Mac ze sady Visual Studio v počítači Windows.

##  <a name="windows"></a> Instalační program Windows v Parallels (Visual Studio a Xamarin)

1.  Použití plochy Windows, kterou jste nakonfigurovali v Parallels VMWare, [stáhněte a spusťte instalační program pro všechny edice sady Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) (Community, Professional nebo Enterprise). Visual Studio 2017 Community je bezplatné edice; edice Professional a Enterprise je možné na základě zkušební verze po dobu 30 dnů.

2.  V rámci instalačního programu, klikněte **další možnosti** tlačítko (ikona tři pruhy) _vedle_ **spuštění** klikněte na tlačítko **změnit**.:

     ![Výběr možnosti upravit v instalaci sady Visual Studio](../cross-platform/media/cross-plat-xamarin-setup-1a.png "1 nastavení různé platformy Xamarin")

3.  Zaškrtněte následující políčka:

    1.  **Mobilní aplikace a hry > vývoj mobilních aplikací pomocí .NET**. To také automaticky vybere různé nástroje pro Android v rámci běžných nástrojů a sad SDK. Tuto možnost byste také aktualizovat žádné stávající instalaci Xamarin.

         ![Vyberte možnost vývoj mobilních řešení v části vývoj mobilní a herní](../cross-platform/media/cross-plat-xamarin-setup-2a.png "různé platformy Xamarin instalace 2")

    2. (Volitelné) **Windows > vývoj pro univerzální platformu Windows**. To zahrnuje možnosti pro instalaci bitové kopie emulátorů, které bude trvat déle stáhnout; Můžete se kdykoli vrátit do instalačního programu sady Visual Studio je přidat později.

4.  Klikněte na tlačítko **změnit** tlačítko a nechat spustit proces. Znovu, bude to trvat delší dobu, během této doby můžete pokračovat s pokyny k instalaci Mac a projděte si [přečtěte si víc o vývoj mobilních řešení s využitím kódu Xamarin](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Po dokončení instalace spusťte Visual Studio a přihlaste se pomocí svého účtu Microsoft po zobrazení výzvy (jedná se o stejný účet pomocí Windows).

6.  Po dokončení instalace Xamarinu na počítače s Windows i Mac, postupujte podle pokynů [připojení k Macu pomocí XMA](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com) tak, aby mohli pracovat s iOS ze sady Visual Studio.

##  <a name="verify"></a> Ověření prostředí

Po dokončení instalační programy, věnujte několik minut, chcete-li ověřit, že je vše připraveno k prostředí vývoj na platformě Xamarin.

### <a name="xamarin-studio"></a>Xamarin Studio

Nejprve, ujistěte se, že přejdete na zadané odkazy, abyste měli **Xamarin Studio** vybrané v pravém horním rohu tak, aby se zobrazí na správnou verzi dokumentace k Xamarinu:

![Vybrat Xamarin Studio naleznete v dokumentaci správné Xamarin.com](../cross-platform/media/crossplat-xamarin-mac-1.png "CrossPlat Xamarin Mac 1")

**Android**

1.  Ověření vytvoření projektu pro Android postupujte podle pokynů [vytvoření projektu Android](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Ověření ladění v emulátoru Androidu prostřednictvím [Android Player > integrace s nástroji Xamarin Studio dokumentaci](https://developer.xamarin.com/guides/android/getting_started/installation/android-player/#Integration_with_Xamarin_Studio) (xamarin.com).

**iOS**

1.  Ověření vytvoření projektu iOS podle pokynů v [vytvoření iOS](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

2.  Ověření ladění v simulátoru iOS prostřednictvím [ladění v dokumentaci k simulátoru](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) (xamarin.com).

### <a name="visual-studio"></a>Visual Studio

Nejprve, ujistěte se, že přejdete na zadané odkazy, abyste měli **sady Visual Studio** vybrané v pravém horním rohu tak, aby se zobrazí na správnou verzi dokumentace k Xamarinu:

![Výběr Visual Studio naleznete v dokumentaci správné Xamarin.com](../cross-platform/media/crossplat-xamarin-mac-2.png "CrossPlat Xamarin Mac 2")

**Android**

1.  Ověření vytvoření projektu pro Android postupujte podle pokynů [vytvoření projektu Android](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Ověření Android designer: v projektu pro Android v Průzkumníku řešení, otevřete **prostředky > rozložení > Main.axml** souboru.

    -   Pokud se zobrazí chyba s oznámením "Nainstalované sady Android SDK je příliš starý.", klikněte na tlačítko **otevřete Android SDK** v dané zprávy a vyberte nejnovější verzi sady SDK, která je k dispozici. Všimněte si, že musíte používat Visual Studio jako správce k aktualizaci sady SDK.

3.  Ověřte, zda se můžete připojit ze sady Visual Studio na emulátor, který je nainstalovaný na vašem počítači Mac.  Výsledek tohoto je, která se zobrazí v seznamu emulátorů, které můžete vybrat z v rámci sady Visual Studio pro ladění Xamarin Playeru.  Chcete-li to provést, postupujte podle pokynů [připojení sady Visual Studio pro Xamarin Android Player](http://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/android-player-with-visual-studio-in-vm/) (xamarin.com).

**iOS**

1.  Ujistěte se, že váš Mac bude dostupný v síti a je spárovaná s aplikací Visual Studio, jak je popsáno v [připojit k počítači Mac](https://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac) (xamarin.com).

2.  Ověření vytvoření projektu iOS podle pokynů v [vytvoření iOS](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

3.  Ověření návrháře scénáře: v projektu pro iOS v Průzkumníku řešení, otevřete **MainStoryboard.storyboard** souboru. Tady je Visual Studio hostitelem designer, na kterém běží vzdáleně na počítači Mac.

4.  Ověření, sestavování a ladění:

    1.  Klikněte pravým tlačítkem na projekt pro iOS v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.

    2.  Vyberte **iPhoneSimulator** cílové sestavení sady Visual Studio rozevíracím seznamu, jak je znázorněno níže. Pokud nejsou uvedeny žádné simulátory, spusťte Xcode na Macu, vyberte **Xcode -> Předvolby**a klikněte na tlačítko **Stáhnout**. V části **součásti** by se měla zobrazit simulátor verze, které jsou k dispozici ke stažení. Další pokyny k ladění můžete najít na Xamarinu pro [ladění](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) stránky (xamarin.com).

         ![Výběr iPhoneSimulator cíl sestavení](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin ověřte 5")

    3.  Vyberte cíl iPhone ladění sady Visual Studio rozevíracím seznamu, jak je znázorněno níže a stisknutím klávesy F5 spusťte ladicí program. Tím se spustí simulátor na Macu, kde budete pracovat s aplikací během ladění se stane v sadě Visual Studio.

         ![Vyberte cíl ladění iPhone](../cross-platform/media/crossplat-xamarin-verify-6.png "6 ověřte CrossPlat Xamarin")