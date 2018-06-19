---
title: Instalace Visual C++ pro vývoj pro různé platformy mobilních | Microsoft Docs
ms.custom: ''
ms.date: 05/21/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
author: corob-msft
ms.author: corob
manager: douge
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 5013f1ce5ed9c20ba51feef7dd73d80adc152103
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
ms.locfileid: "34454698"
---
# <a name="install-cross-platform-mobile-development-with-c"></a>Nainstalovat pro vývoj mobilních řešení pro různé platformy s C++

C++ v sadě Visual Studio můžete použít k vytvoření aplikace Windows Desktop, aplikace pro univerzální platformu Windows (UWP), aplikace Linux a nyní aplikace pro Android a iOS. **Pro vývoj mobilních řešení s jazykem C++** zatížení je sada instalovatelných komponent v sadě Visual Studio, která zahrnuje různé platformy iOS, Android a UWP Visual Studio šablony. Nainstaluje nástroje napříč platformami a sady SDK potřebujete začít rychle, aniž by museli najít, stahování a nakonfigurovat sami. Můžete pomocí těchto nástrojů v sadě Visual Studio můžete snadno vytvořit, upravit, ladění a testování vašich projektů napříč platformami. Toto téma popisuje postup instalace nástroje a software jiných výrobců, které jsou potřebné k vývoji aplikací pro různé platformy v jazyce C++ pomocí sady Visual Studio. Přehled najdete v tématu [Mobile napříč platformami Visual C++](https://go.microsoft.com/fwlink/p/?LinkId=536383)

## <a name="requirements"></a>Požadavky

- Požadavky na instalaci, najdete v části [produktu rodiny požadavky sady Visual Studio](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs).

   > [!IMPORTANT]
   > Pokud používáte systém Windows 7 nebo Windows Server 2008 R2, můžete vyvíjet kódu pro aplikace Windows Desktop, aplikace Android nativní aktivity a knihovny a aplikace a knihovny kódu pro iOS, ale ne Windows Phone nebo UWP aplikací.

Můžete vytvářet aplikace pro specifické platformy zařízení, jsou některé další požadavky:

- Windows Phone emulátory a Microsoft Visual Studio Emulator for Android vyžadují počítač, který můžete spustit technologie Hyper-V. Než bude možné nainstalovat a spustit emulátorů, musí být povolena funkce technologie Hyper-V v systému Windows. Další informace najdete v tématu o emulátor [požadavky na systém](system-requirements-for-the-visual-studio-emulator-for-android.md).

- X86, které nejlépe fungovat Android emulátorů, které jsou součástí sady SDK pro Android na počítačích, které můžete spustit Intel HAXM ovladače. Tento ovladač vyžaduje procesor Intel x64 s podporou spuštění zakázat Bit a VT-x. Další informace najdete v tématu [Intel® hardwaru Accelerated správce spuštění (Intel® HAXM)](https://go.microsoft.com/fwlink/p/?LinkId=536385).

- Vytváření kódu pro iOS vyžaduje Apple ID, účet programu pro vývojáře iOS a počítač Mac, který můžete spustit [Xcode](https://go.microsoft.com/fwlink/p/?LinkId=536387) verze 6 nebo novější na OS X Mavericks (verze 10.9) nebo novější verze. Odkaz na postup instalace, najdete v části [instalace nástrojů pro iOS](#install-tools-for-ios).

## <a name="get-the-tools"></a>Získat nástroje

Mobilní vývoj s jazykem C++ je k dispozici v edicích Visual Studio Community, Professional a Enterprise. Visual Studio, přejděte do [Visual Studio stáhne](https://go.microsoft.com/fwlink/p/?linkid=517106) stránky. Nástroje pro vývoj pro různé platformy mobilních jsou dostupné od v sadě Visual Studio 2015 Update 2 nebo novější.

## <a name="install-the-tools"></a>Nainstalujte nástroje

Instalační program Visual Studio pro Visual Studio 2017 zahrnuje **pro vývoj mobilních řešení s jazykem C++** zatížení, který nainstaluje nástroje pro jazyk C++, šablony a komponent potřebných pro vývoj v sadě Visual Studio pro Android a iOS. Nainstaluje RSZ a Clang modulové, které jsou potřebné pro Android sestavení a ladění a součásti pro komunikaci s počítačem Mac pro vývoj pro iOS. Nainstaluje taky všechny nástroje třetích stran a software development Kit, které jsou potřebné k podpoře vývoj aplikace pro Android a iOS. Většina těchto nástrojů jiných výrobců jsou open-source softwaru, které jsou potřebné pro podporu platformu Android.

- Android Kit nativní vývoj (NDK) je potřeba vytvořit kódu C++, která je cílena platformu Android.

- Android SDK, Apache Ant a Java SE Development Kit jsou vyžadovány pro proces Android sestavení.

- Emulátor Google Android a správce spuštění Accelerated hardwaru Intel jsou volitelné, ale nedoporučuje, součásti. Můžete vyvíjet a ladit přímo na zařízení se systémem Android, ale často je jednodušší použít emulátoru na ploše pro ladění. Microsoft Visual Studio Emulator poskytuje pro Android, která je možné nainstalovat odděleně.

#### <a name="to-install-the-mobile-development-with-c-workload-in-visual-studio-2017"></a>Chcete-li nainstalovat mobilní vývoj zatížení C++ ve Visual Studio 2017

1. Spustit **instalační program Visual Studio** z **spustit** nabídky.

1. Pokud jste již nainstalovali Visual Studio, vyberte **upravit** tlačítko pro nainstalovanou verzi Visual Studia, kterou chcete upravit. Jinak, vyberte **nainstalovat** k instalaci sady Visual Studio.

1. S **úlohy** vybrána karta, přejděte dolů a vyberte **pro vývoj mobilních řešení s jazykem C++** zatížení v instalačním programu Visual Studio. Pokud je vybraná tato zatížení, jsou vybrány také další požadované součásti pro vývoje v jazyce C++. Můžete také další úlohy a jednotlivých součástí k instalaci ve stejnou dobu. Chcete-li vytvořit napříč platformami kód, který také cílí UPW, vyberte **vývoj pro univerzální platformu Windows** zatížení.

1. V **podrobné informace o instalaci** podokně rozbalte **pro vývoj mobilních řešení s jazykem C++**. V **volitelné** části, můžete vybrat další verze na NDK, emulátor Google Android, Správce spuštění Accelerated Intel hardwaru a IncrediBuild sestavení akcelerace nástroj.

1. Ve výchozím nastavení jsou zahrnuty jeden nebo více součásti instalace sady SDK pro Android úlohy. Jsou dostupné další verze sady SDK pro Android. Přidat do instalace, vyberte **jednotlivých součástí** a potom přejděte dolů k položce **sady SDK, knihovny a rozhraní** část, aby váš výběr.

1. Vyberte **upravit** nebo **nainstalovat** tlačítko k instalaci **pro vývoj mobilních řešení s jazykem C++** zatížení a dalších vybrané úlohy a volitelné součásti.

   Po dokončení instalace ukončete instalační program a potom restartujte počítač. Některé akce instalace pro komponenty jiných výrobců se projeví až po restartování počítače.

   > [!IMPORTANT]
   > Je nutné restartovat a ujistěte se, že se vše správně nainstalovalo.

1. Otevřete Visual Studio. Pokud je při prvním spuštění sady Visual Studio, může trvat nějakou dobu ke konfiguraci a přihlaste se. Když Visual Studio je připraveno, zkontrolujte všechny aktualizace a nainstalovány.

#### <a name="to-install-the-mobile-development-component-and-third-party-tools-in-visual-studio-2015"></a>Chcete-li nainstalovat vývoj mobilních řešení pro komponenty a nástroje třetích stran v sadě Visual Studio 2015

Pokud používáte Visual Studio 2015, jeho instalační program zahrnuje možnost nainstalovat Visual C++ pro vývoj napříč platformami mobilních řešení, který se nainstaluje požadované nástroje jazyka C++, šablony a součásti v sadě Visual Studio 2015.

1. Spusťte instalační program sady Visual Studio 2015. Chcete-li nainstalovat volitelné součásti, zvolte **vlastní** jako typ instalace. Zvolte **Další** vyberte volitelné součásti k instalaci.

1. V **vyberte funkce**, rozbalte položku **vývoj pro různé platformy Mobile** a zkontrolujte **Visual C++ vývoj mobilních řešení**.

   ![Vyberte Visual C&#43; &#43; pro vývoj mobilních řešení](../cross-platform/media/cppmdd_install_vcmdd.png "CPPMDD_Install_VCMDD")

   Ve výchozím nastavení, když vyberete **Visual C++ vývoj mobilních řešení**, **programovací jazyky** je možnost nastavena k instalaci **Visual C++** a **běžné nástroje pro a Software Development Kit** jsou nastavené možnosti instalace požadovaných součástí třetích stran. Pokud je potřebujete, můžete zvolit další součásti. Ve výchozím nastavení **Microsoft Visual Studio Emulator for Android** , vybere se také. Neaktivní v seznamu se zobrazí součásti, které jsou již nainstalovány.

   K sestavení univerzální aplikace pro Windows a jejich sdílení v kódu mezi nimi a vašich projektů Android a iOS **vyberte funkce**, rozbalte položku **Windows a vývoj webů** a zkontrolujte **univerzální aplikace pro Windows Nástroje pro vývoj**. Pokud nemáte v úmyslu vytvořit univerzální aplikace pro Windows, můžete přeskočit tuto možnost.

   Zvolte **Další** pokračujte.

1. Komponenty třetích stran mají své vlastní licenční podmínky. Licenční podmínky můžete zobrazit výběrem **licenční podmínky** odkaz vedle jednotlivých součástí. Zvolte **nainstalovat** přidejte součásti a instalace sady Visual Studio a Visual C++ pro vývoj mobilních řešení pro různé platformy.

1. Po dokončení instalace ukončete instalační program a potom restartujte počítač. Některé akce instalace pro komponenty jiných výrobců se projeví až po restartování počítače.

   > [!IMPORTANT]
   > Je nutné restartovat a ujistěte se, že se vše správně nainstalovalo.

   Pokud emulátor Microsoft Visual Studio pro Android součásti se nepodařilo nainstalovat, váš počítač nemusí mít Hyper-V povolena. Použití **Windows zapnout nebo vypnout funkce** aplikace ovládacích panelů povolit technologie Hyper-V, a poté znovu spusťte instalační program sady Visual Studio.

   > [!NOTE]
   > Pokud váš počítač nebo vaši verzi systému Windows nepodporuje technologie Hyper-V, nebudete moct používat emulátor sady Microsoft Visual Studio pro Android součást. Domů edice systému Windows nezahrnuje podpory technologie Hyper-V.

1. Otevřete Visual Studio. Pokud je při prvním spuštění sady Visual Studio, může trvat nějakou dobu ke konfiguraci a přihlaste se. Když je připraven, v sadě Visual Studio **nástroje** nabídce vyberte možnost **rozšíření a aktualizace**, **aktualizace**. Pokud že Visual Studio aktualizace k dispozici pro Visual C++ pro vývoj mobilních řešení pro různé platformy, nebo pro Microsoft Visual Studio Emulator for Android, je nainstalujte.

## <a name="install-tools-for-ios"></a>Instalace nástrojů pro iOS

Visual C++ pro vývoj mobilních řešení pro různé platformy můžete upravit, ladění a nasazení iOS kódu simulátoru iOS nebo zařízení s iOS, ale kvůli licenční omezení, kód musí být vytvořen vzdáleně v počítačích Mac. Sestavení a spuštění aplikace pro iOS pomocí sady Visual Studio, musíte nastavit a nakonfigurovat vzdáleného agenta na vaše Mac. Podrobné pokyny k instalaci, požadavky a možnosti konfigurace najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](install-and-configure-tools-to-build-using-ios.md). Pokud nejsou vytvářet pro iOS, můžete tento krok přeskočit.

## <a name="install-or-update-dependencies-manually"></a>Instalace nebo ručně aktualizovat závislosti

Pokud se rozhodnete nainstalovat jeden nebo více závislostí třetích stran při instalaci pomocí instalačního programu sady Visual Studio **pro vývoj mobilních řešení s jazykem C++** zatížení (nebo v sadě Visual Studio 2015, Visual C++ vývoj mobilních řešení možnost), můžete můžete je nainstalovat později pomocí kroků v [nainstalovat nástroje](#install-the-tools). Instalační program Visual Studio se pravidelně aktualizuje nainstalovat nejnovější komponenty jiných výrobců. Můžete ho nainstalovat aktualizované sady SDK a NDKs. Můžete také nainstalovat nebo je aktualizovat nezávisle na Visual Studio.

> [!CAUTION]
> Závislosti můžete nainstalovat v libovolném pořadí, s výjimkou Java. Musíte nainstalovat a nakonfigurovat sadu JDK, před instalací sady SDK pro Android.

Přečtěte si následující informace a použijte tyto odkazy ruční instalace závislosti.

- [Java SE Development Kit](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

   Ve výchozím nastavení převede instalační program nástroje Java v C:\Program Files (x86) \Java.

- [Android SDK](https://developer.android.com/sdk/index.html#command-tools)

   Během instalace aktualizace rozhraní API podle doporučení. Ujistěte se, že aspoň je nainstalována sada SDK pro Android 5.0 typu Lupa (API úrovně 21). Ve výchozím nastavení převede instalační program sady SDK pro Android v C:\Program Files (x86) \Android\android-sdk.

   SDK Manager aplikaci můžete spustit v adresáři sady SDK pro Android znovu a aktualizovat sadu SDK a instalaci volitelných nástrojů a další úrovně rozhraní API. Aktualizace se pravděpodobně nepodaří nainstalovat, pokud nechcete použít **spustit jako správce** aplikace SDK Manager spustit. Pokud máte potíže s vytváření aplikace pro Android, zkontrolujte SDK Manager aktualizace vašeho nainstalované sady SDK.

   Používat některé z Android emulátorů, které jsou součástí sady SDK pro Android, musíte nainstalovat volitelné Intel HAXM ovladače. Možná budete muset odebrat funkce Hyper-V ze systému Windows k instalaci ovladačů Intel HAXM úspěšně. Je nutné obnovit funkce Hyper-V použít emulátorů Windows Phone a emulátor sady Microsoft Visual Studio pro Android. Další informace najdete v tématu [Android emulátoru hardwarovou akceleraci](https://docs.microsoft.com/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin).

- [Android NDK](https://developer.android.com/tools/sdk/ndk/index.html)

   Ve výchozím nastavení instalační program převádí na C:\ProgramData\Microsoft\AndroidNDK Android NDK. Můžete stáhnout a nainstalovat Android NDK znovu, aby NDK instalace aktualizace.

- [Apache Ant](https://ant.apache.org/bindownload.cgi)

   Ve výchozím nastavení instalační program vloží Apache Ant C:\Program Files (x86) \Microsoft Visual Studio 14.0\Apps.

- [Emulátor Microsoft Visual Studio pro Android](https://aka.ms/vscomemudownload)

   Microsoft Visual Studio Emulator for Android je užitečné pro testování a ladění kódu volitelné emulátor. Po vydání Visual Studio Emulator for Android Google aktualizovat jejich emulátoru Android použít hardwarovou akceleraci prostřednictvím Intel je HAXM. Doporučujeme že používat Zrychlený emulátor Google Pokud je to možné, protože nabízí přístup k nejnovější operační systém Android bitové kopie a webu Google Play services.

Ve většině případů lze zjistit sady Visual Studio konfigurace pro software třetích stran, které jste nainstalovali a udržuje cesty instalace v proměnných prostředí interní. Můžete přepsat výchozí cesty těchto nástrojů pro vývoj pro různé platformy v integrovaném vývojovém prostředí sady Visual Studio.

#### <a name="to-set-the-paths-for-third-party-tools"></a>Chcete-li nastavit cesty pro nástroje třetích stran

1. V řádku nabídek Visual Studio, vyberte **nástroje** > **možnosti**.

1. V **možnosti** dialogové okno, vyberte **křížové platformy** > **C++** > **Android**.

   ![Nástroj pro Android cesta možnosti](../cross-platform/media/cppmdd_options_android.PNG "CPPMDD_Options_Android")

1. Chcete-li změnit tuto cestu používají nástroj, zaškrtněte políčko vedle cestu a upravit cesta ke složce, do textového pole. Můžete také použít tlačítko pro procházení (**...** ) Chcete-li otevřít **vyberte umístění** dialogové okno a vyberte složku.

1. Zvolte **OK** uložit vlastní nástroj umístění složek.

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace nástrojů pro vytváření pomocí iOS](install-and-configure-tools-to-build-using-ios.md)
- [Visual C++ a platformy Mobile](https://go.microsoft.com/fwlink/p/?LinkId=536383)
