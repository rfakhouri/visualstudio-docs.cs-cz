---
title: Nainstalovat Xamarin pro Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 62871cefc6d5b4f54d56ea17f04774d9d91b9984
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254950"
---
# <a name="setup-and-install"></a>Nastavení a instalace

Vytvářet nativní aplikace pro iOS, Android a Windows aplikace z běžných C# / kód .NET základní pomocí Xamarin, potřebujete následující hardware a software:

-   Pro práci s Windows a aplikací pro Android: vývoj počítači Windows (ne virtuální počítač) s Visual Studio 2017 (včetně funkce pro vývoj Xamarin) nainstalována.  

-   Pro práci s aplikacemi pro iOS: Mac s systému macOS Sierra 10.12 nebo vyšší, s Xcode nainstalován a Visual Studio pro Mac, které jsou nainstalované.

K použití platformě Xamarin se vyžaduje bez samostatné licence.
 
Můžete nastavit systému Windows a počítače Mac ve stejnou dobu, a v době spuštění těchto instalační programy můžete přejít [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md) ke čtení a podívejte se na pozadí nezbytné materiálů.

Pokud máte problémy s platformou Xamarin po provedení tohoto nastavení a instalaci, vystavte tady svůj dotaz na [forums.xamarin.com](http://forums.xamarin.com/).

<a name="prereq" /> 

## <a name="pre-requisites"></a>Předpoklady

###  <a name="for-targeting-windows-and-android"></a>Pro cílení na Windows a Android

V tématu [2017 produktu rodiny požadavky sady Visual Studio](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs) pro podrobné požadavky pro instalaci Visual Studio 2017.

Nainstalujte Visual 2017 na fyzickém počítači Windows (ne virtuální počítač) s Windows 10 nainstalované všechny aktualizace. 

### <a name="for-targeting-ios"></a>Pro cílení na iOS

Pro cíl iOS emulátorů a zařízení z vašeho počítače Windows budete také potřebovat síťových Mac nebo Mac malé systémem systému macOS 10.12 nebo novějším a Xcode 8.3. V tématu [instalační program a nainstalujte Visual Studio pro Mac](/visualstudio/mac/installation.md) další požadavky.

<a name="windows" /> 

##  <a name="windows-setup-visual-studio-and-xamarin"></a>Instalační program systému Windows (Visual Studio a Xamarin)

Pokud jste ještě nenainstalovali Visual Studio 2017, proveďte následující kroky:

1.  [Stáhněte a spusťte instalační program pro všechny edice Visual Studio 2017](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) (Community, Professional a Enterprise). Visual Studio 2017 Community je edice free. Po dobu 30 dnů, po které je nutné licence jsou k dispozici na základě zkušební edice Professional a Enterprise.

2.  Když **instalace** otevře se dialogové okno, zkontrolujte následující pole:    

    - **Mobilní a herní > pro vývoj mobilních řešení s .NET**. Tato možnost také automaticky vybere různé nástroje pro Android a Software Development Kit. 

        ![Vyberte možnost vývoj mobilních řešení v rámci herní a vývoj mobilních řešení pro](../cross-platform/media/cross-plat-xamarin-setup-2a.png "Cross-Plat Xamarin instalace 2")

    - (Volitelné) **Windows > vývoj pro univerzální platformu Windows**. 

Pokud už máte Visual Studio 2017 nainstalován, ale ještě nenainstalovali platformě Xamarin, proveďte následující kroky:

1. Spustit **instalační program Visual Studio** z **spustit** nabídky.

2.  V rámci instalačního programu, klikněte na **Další** tlačítko a potom vyberte **upravit**:

    ![Vyberete možnost upravit v instalaci sady Visual Studio](../cross-platform/media/cross-plat-xamarin-setup-1a.png "Cross-Plat Xamarin instalační 1")

3.  Když **instalace** otevře se dialogové okno, zkontrolujte **mobilní a herní > vývoj mobilních řešení pomocí rozhraní .NET** a (volitelně) **Windows > vývoj pro univerzální platformu Windows**. **Vývoj mobilních řešení s .NET** možnost by měl aktualizovat také případné existující instalace Xamarin.

Při instalaci, můžete pokračovat s pokyny pro instalaci Mac a projít [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Po dokončení instalace spusťte Visual Studio a přihlaste se pomocí účtu Microsoft, pokud se zobrazí výzva. Tento účet je stejného účtu, který budete používat v systému Windows.

6.  Pro testování aplikací pro Android, použijte [emulátoru Android SDK](/xamarin/android/get-started/installation/android-emulator/) Pokud nemáte fyzického zařízení s Androidem. 

<a name="mac" />

##  <a name="mac-setup-apple-id-xcode-and-xamarin"></a>Instalační program MAC (Apple ID, Xcode a Xamarin)

1.  Vytvoření volné Apple ID na [ https://appleid.apple.com ](https://appleid.apple.com/) Pokud již nemáte. Toto Apple ID je nutné pro instalaci a přihlášení k Xcode.

2.  Stáhněte a nainstalujte Xcode z [ https://developer.apple.com/xcode/ ](https://developer.apple.com/xcode/), a přidejte Apple ID, jak je popsáno na [přidání si účet na Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).

3.  Stáhněte a nainstalujte Visual Studio pro Mac podle pokynů [instalační program a nainstalujte Visual Studio pro Mac](/visualstudio/mac/installation).

4.  Po dokončení instalace Xamarin v počítačích se systémy Windows a Mac, postupujte podle pokynů [připojení k počítači Mac](/xamarin/ios/get-started/installation/windows/connecting-to-mac/) , aby mohl pracovat s iOS a Mac ze sady Visual Studio v počítači s Windows.

Oba počítače musí být ve stejné místní síti.
