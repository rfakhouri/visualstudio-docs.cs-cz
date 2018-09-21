---
title: Nainstalujte si Xamarin pro Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 045b7745d8d9d171560546e893e89ea6cebe1b6f
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495892"
---
# <a name="setup-and-install"></a>Nastavení a instalace

K sestavení nativních aplikací pro iOS, Android a Windows aplikace z common jazyka C# / základu kódu .NET pomocí Xamarinu, potřebujete následující hardware a software:

-   Pro práci s Windows a aplikace pro Android: Windows vývojovém počítači (ne virtuální počítač) pomocí sady Visual Studio 2017 (včetně funkce Xamarin pro vývoj) nainstalovaný.

-   Pro práci s aplikacemi pro iOS: Mac v systému macOS Sierra 10.12 nebo vyšší, s Xcode nainstalovaný a Visual Studio pro Mac, které jsou nainstalované.

Bez samostatné licence je potřeba použít platformu Xamarin.

Můžete nastavit Windows a počítače Mac ve stejnou dobu, a jsou spuštěné tyto instalační programy můžete projít [přečtěte si víc o vývoj mobilních řešení s využitím kódu Xamarin](../cross-platform/learn-about-mobile-development-with-xamarin.md) ke čtení a podívejte se na materiál nezbytné pozadí.

Pokud máte problémy s využitím platformy Xamarin po provedení tohoto nastavení a instalaci, zveřejněte svůj dotaz na [forums.xamarin.com](http://forums.xamarin.com/).

<a name="prereq" />

## <a name="pre-requisites"></a>Předpoklady

###  <a name="for-targeting-windows-and-android"></a>Pro cílení na Windows a Android

Zobrazit [požadavky na systém pro produktovou řadu sady Visual Studio 2017](/visualstudio/productinfo/vs2017-system-requirements-vs) pro podrobné požadavky pro instalaci sady Visual Studio 2017.

Instalovat Visual 2017 ve fyzickém počítači Windows (ne virtuální počítač) s Windows 10 se nainstalují všechny aktualizace.

### <a name="for-targeting-ios"></a>Pro cílení na iOS

Cíl iOS emulátorů a zařízení z počítače Windows budete také potřebovat síťové Mac nebo Mac mini s macOS 10.12 nebo novější a Xcode 8.3. Zobrazit [nastavení a instalaci sady Visual Studio pro Mac](/visualstudio/mac/installation) podrobnější požadavky.

<a name="windows" />

##  <a name="windows-setup-visual-studio-and-xamarin"></a>Nastavení Windows (Visual Studio a Xamarin)

Pokud jste ještě nenainstalovali aplikaci Visual Studio 2017, proveďte následující kroky:

1.  [Stáhněte si a spusťte instalační program pro všechny edice sady Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) (Community, Professional nebo Enterprise). Visual Studio 2017 Community je bezplatné edice. Edice Professional a Enterprise jsou k dispozici na základě zkušební verze po dobu 30 dnů, po jejichž uplynutí je nezbytné licenci.

2.  Když **instalace** se zobrazí dialogové okno, zaškrtněte následující políčka:

    - **Mobilní aplikace a hry > vývoj mobilních aplikací pomocí .NET**. Tato možnost také automaticky vybere různé nástroje pro Android a Software Development Kit.

        ![Vyberte možnost vývoj mobilních řešení v části vývoj mobilní a herní](../cross-platform/media/cross-plat-xamarin-setup-2a.png "různé platformy Xamarin instalace 2")

    - (Volitelné) **Windows > vývoj pro univerzální platformu Windows**.

Pokud už máte nainstalovanou sadu Visual Studio 2017, ale ještě nenainstalovali platformu Xamarin, proveďte následující kroky:

1. Spustit **instalační program sady Visual Studio** z **Start** nabídky.

2.  V rámci instalačního programu, klikněte **Další** tlačítko a pak zvolte **změnit**:

    ![Výběr možnosti upravit v instalaci sady Visual Studio](../cross-platform/media/cross-plat-xamarin-setup-1a.png "1 nastavení různé platformy Xamarin")

3.  Když **instalace** se zobrazí dialogové okno, zkontrolujte **mobilní aplikace a hry > vývoj mobilních aplikací pomocí .NET** a (volitelně) **Windows > vývoj pro univerzální platformu Windows**. **Vývoj mobilních aplikací pomocí .NET** možnost by měl také aktualizovat žádné stávající instalaci Xamarinu.

Během instalace můžete pokračovat s pokyny k instalaci Mac a projděte si [přečtěte si víc o vývoj mobilních řešení s využitím kódu Xamarin](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Po dokončení instalace spusťte Visual Studio a přihlaste se pomocí účtu Microsoft, pokud se zobrazí výzva. Tento účet se o stejný účet, který používáte s Windows.

6.  Pro testování aplikací pro Android, použijte [emulátoru sady SDK pro Android](/xamarin/android/get-started/installation/android-emulator/) Pokud nemáte fyzické zařízení s Androidem.

<a name="mac" />

##  <a name="mac-setup-apple-id-xcode-and-xamarin"></a>Nastavení MAC (Apple ID, Xcode a Xamarin)

1.  Vytvořit bezplatný Apple ID na [ https://appleid.apple.com ](https://appleid.apple.com/) Pokud již nemáte. Toto Apple ID je nezbytné pro instalaci a přihlášení do Xcode.

2.  Stáhněte a nainstalujte Xcode z [ https://developer.apple.com/xcode/ ](https://developer.apple.com/xcode/), a přidejte svoje Apple ID, jak je popsáno na [přidání účtu do Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).

3.  Stažení a instalaci sady Visual Studio pro Mac podle pokynů v [nastavení a instalaci sady Visual Studio pro Mac](/visualstudio/mac/installation).

4.  Po dokončení instalace Xamarinu na počítače s Windows i Mac, postupujte podle pokynů [připojení k Macu](/xamarin/ios/get-started/installation/windows/connecting-to-mac/) , což umožní pracovat s iOS a Mac ze sady Visual Studio v počítači Windows.

Oba počítače musí být ve stejné místní síti.
