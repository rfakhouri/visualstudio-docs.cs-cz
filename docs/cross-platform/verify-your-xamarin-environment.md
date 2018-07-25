---
title: Ověření prostředí Xamarinu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 83dfac08058e8b01b6c6d007461f3468e91b396c
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233084"
---
# <a name="verify-your-xamarin-environment"></a>Ověření prostředí Xamarinu

Po dokončení instalační programy (viz [nastavení a instalaci](../cross-platform/setup-and-install.md)), věnujte několik minut, chcete-li ověřit, že je vše připraveno k prostředí vývoj na platformě Xamarin.

 Po dokončení ověření instalace, zkuste jednu nebo obě z následujících návodech:

-   [Základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md) k sestavení aplikace Xamarin.Forms.

-   [Vytvářejte aplikace s nativním uživatelským rozhraním pomocí Xamarinu v sadě Visual Studio](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md) používat nativní uživatelská rozhraní na jednotlivých platformách ale sdílení kódu v knihovně .NET Standard.

## <a name="all-platforms"></a>Všechny platformy

V sadě Visual Studio, vyberte nejdřív **nástroje** > **rozšíření a aktualizace** a zaškrtněte políčko, pokud některé z těchto komponent Xamarin vyžadovat aktualizace.

Pak vytvořte nové řešení Xamarin.Forms v sadě Visual Studio pomocí **souboru** > **nový projekt**. V dialogovém okně rozbalte **Visual C#** > **Cross-Platform**vyberte **mobilní aplikace (Xamarin.Forms)** a klikněte na tlačítko **OK**. V dialogovém okně, který následuje, vyberte **prázdnou aplikaci**. V části **strategie sdílení kódu**vyberte **.NET Standard**. Klikněte na tlačítko **OK**.

Tyto akce vytvořit řešení se čtyřmi projekty: projekt sdílené knihovny .NET Standard 2.0 a projekty aplikací pro Android, iOS a univerzální platformu Windows (UPW):

![Vytvoření nového projektu z šablony prázdné aplikace Xamarin.Forms výsledky](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin ověřte 1")

## <a name="android"></a>Android

1. Zkontrolujte, že máte nainstalované tak, že přejdete na nejnovější nástroje sady Android SDK **nástroje > Android > správce sady Android SDK**. Nainstalujte nejnovější verze sady Android SDK Tools, nástroje pro platformu Android SDK a Android SDK Build tools. Není nutné vždy nainstalujte nejnovější rozhraní Android API úrovně. Úroveň rozhraní API, které potřebujete, závisí na úrovni platformy, kterou chcete cílit. Obecně platí instalace platformu Xamarin nainstaluje úroveň platformy Android, které vyžaduje.

2.  Ověření, sestavování a ladění na zařízení nebo emulátoru:

    -   Klikněte pravým tlačítkem na projekt pro Android v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.

    -   Na panelu nástrojů měli byste vidět rozevíracího seznamu, který obsahuje seznam emulátory a zařízení se systémem Android k dispozici.

    Zařízení s androidem musí být povolena pro ladění v možnosti pro vývojáře o stránku s nastavením zařízení USB. Zařízení je pak připojen k počítači pomocí kabelu USB.

    Emulátory jsou také uvedeny. Vyberte jednu z zařízení nebo emulátorů sady Visual Studio:

  ![Vyberte Visual Studio Emulator for Android jako cíl ladění](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin ověřte 3")

  Další informace najdete v tématu [představení sady Visual Studio Emulator for Android](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (blogu Visual Studio ALM). Pokud narazíte na problémy, získávání emulátor fungovat najdete v tématu [řešení potíží s Visual Studio Emulator for Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md). Můžete také vytvořit nové profily zařízení pro emulátor serveru tak, že vyberete **nástroje > Android > Správce emulátoru Androidu**.

3. Stisknutím klávesy **F5** ke kompilaci a program nasadit do zařízení s Androidem nebo emulátoru.

## <a name="windows"></a>Windows

1.  Klikněte pravým tlačítkem na projekt Universal Windows v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.

2.  V **platformy řešení** rozevíracího seznamu, vyberte **x86** nebo **x64**. Vyberte **místního počítače**.

3.  Stisknutím klávesy **F5** k nasazení programu na ploše.

## <a name="ios"></a>iOS

1.  Ujistěte se, že váš Mac bude dostupný v síti a je spárovaná s aplikací Visual Studio, jak je popsáno na [připojení k Macu](/xamarin/ios/get-started/installation/windows/connecting-to-mac/).

2.  Klikněte pravým tlačítkem na projekt pro iOS v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.

3.  Vyberte **iPhoneSimulator** cílové sestavení sady Visual Studio rozevíracím seznamu, jak je uvedeno níže, nebo **iPhone** cílit, pokud máte zařízení připojeném k počítači Mac.

 ![Výběr iPhoneSimulator cíl sestavení](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin ověřte 5")

 Pokud nejsou uvedeny žádné simulátory, spusťte Xcode na Macu, vyberte **Xcode** > **Předvolby**a klikněte na tlačítko **Stáhnout**. V části **součásti** záhlaví jste měli vidět simulátor verze, které jsou k dispozici ke stažení. Další návod pro ladění k dispozici na [iOS ladění](/xamarin/ios/deploy-test/debugging-in-xamarin-ios) stránky.

4.  Vyberte cíl emulátor zařízení z rozevírací nabídky sady Visual Studio:

 ![Vyberte cíl ladění iPhone](../cross-platform/media/crossplat-xamarin-verify-6.png "6 ověřte CrossPlat Xamarin")

5. Spusťte ladicí program stisknutím kombinace kláves **F5**. Simulátor se spouští na počítači Mac, kde budete pracovat s aplikací během ladění se stane v sadě Visual Studio. Pokud už máte fyzické zařízení iPhone nebo iPad připojené k počítači Mac, se zobrazí v seznamu a můžete ho vybrat místo toho. Pokud nevidíte žádné zařízení nebo simulátoru uvedené, zkontrolujte připojení k počítači Mac. Přečtěte si článek propojené výše v kroku 1, nebo přejít na **nástroje** > **iOS** > **spárovat s počítačem Mac**

6.  Pokud narazíte na potíže s připojením k počítači Mac, přečtěte si [řešení potíží s připojením](/xamarin/ios/get-started/installation/windows/connecting-to-mac/troubleshooting/).

7.  Pokud se zobrazí chyba s oznámením "žádné nainstalované zřizovací profily odpovídají nainstalovaných iOS podpisových klíčů", vyzkoušejte následující návrhy:

  - Zkontrolujte, že váš účet Apple Id, které se přidá v Xcode na počítači Mac, jak je popsáno v [přidání účtu do Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  Po přidání vašeho účtu, je potřeba restartovat Visual Studio a Xcode.

  - Ověřte v iOS sadu vlastností projektu v systému iOS podpisový kartu, nic pole vlastní oprávnění pro ladění aktivní konfiguraci.  Poznámka: pouze snažte odebrání toto nastavení, pokud jste se setkali výše chybová zpráva.

  ![CrossPlat Xamarin ověřte 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin ověřte 8")
