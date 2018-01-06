---
title: "Instalace Visual C++ pro vývoj pro různé platformy mobilních | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: xplat-cplusplus
ms.openlocfilehash: d677c74d44f1ddc0b250d6763cef4738cd642832
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="install-visual-c-for-cross-platform-mobile-development"></a>Instalace Visual C++ pro vývoj mobilních pro různé platformy
[Visual C++ pro vývoj mobilních řešení pro různé platformy](http://go.microsoft.com/fwlink/p/?LinkId=536383) je instalovatelných komponent sady Visual Studio 2015. Zahrnuje šablony sady Visual Studio napříč platformami a nainstaluje nástroje napříč platformami a sady SDK začít rychle, aniž by museli najít, stahování a nakonfigurovat sami. Tyto nástroje můžete v sadě Visual Studio snadno vytvořit, upravit, ladit a testovat projekty napříč platformami. Toto téma popisuje postup instalace nástroje a software jiných výrobců, které jsou potřebné k vývoji aplikací pro různé platformy pomocí sady Visual Studio. Přehled součásti najdete v tématu [Mobile napříč platformami Visual C++](http://go.microsoft.com/fwlink/p/?LinkId=536387)  
  
 [Požadavky](#Requirements)   
 [Získat nástroje](#GetTheTools)   
 [Nainstalujte nástroje](#InstallTheTools)   
 [Instalace nástrojů pro iOS](#InstallForiOS)   
 [Instalace nebo ručně aktualizovat závislosti](#ThirdParty)  
  
##  <a name="Requirements"></a>Požadavky  
  
-   Požadavky na instalaci, najdete v části [systémové požadavky sady Visual Studio 2015](https://www.visualstudio.com/visual-studio-2015-system-requirements-vs).  
  
    > [!IMPORTANT]
    >  Pokud používáte systém Windows 7 nebo Windows Server 2008 R2, můžete vyvíjet kódu pro aplikace klasické systému Windows, aplikace Android nativní aktivity a knihovny a aplikace a knihovny kódu pro iOS, ale ne aplikace Windows Store nebo Universal Windows.  
  
 Můžete vytvářet aplikace pro specifické platformy zařízení, jsou některé další požadavky:  
  
-   Windows Phone emulátory a Microsoft Visual Studio Emulator for Android vyžadují počítač, který můžete spustit technologie Hyper-V. Než bude možné nainstalovat a spustit emulátorů, musí být povolena funkce technologie Hyper-V v systému Windows. Další informace najdete v tématu o emulátor [požadavky na systém](http://msdn.microsoft.com/en-us/4d5bb438-231a-4cd2-84b7-e9660b0e3baf).  
  
-   X86, které nejlépe fungovat Android emulátorů, které jsou součástí sady SDK pro Android na počítačích, které můžete spustit Intel HAXM ovladače. Tento ovladač vyžaduje procesor Intel x64 s podporou spuštění zakázat Bit a VT-x. Další informace najdete v tématu [pokyny k instalaci pro Intel® hardwaru Accelerated správce spuštění – Microsoft Windows](http://go.microsoft.com/fwlink/p/?LinkId=536385).  
  
-   Vytváření kódu pro iOS vyžaduje Apple ID, účet programu pro vývojáře iOS a počítač Mac, který můžete spustit [Xcode 6](http://go.microsoft.com/fwlink/p/?LinkId=536387) nebo pozdější OS X Mavericks nebo novější verze. Jednoduché instalační pokyny najdete v tématu [instalace nástrojů pro iOS](#InstallForiOS).  
  
##  <a name="GetTheTools"></a>Získat nástroje  
 Visual C++ pro vývoj mobilních řešení pro různé platformy je součástí verze Visual Studio Community, Professional a Enterprise instalovatelných komponent. Visual Studio, přejděte do [Visual Studio 2015 stáhne](http://go.microsoft.com/fwlink/p/?linkid=517106) stránky a stáhněte si Visual Studio 2015 s aktualizací 2 nebo novější.  
  
##  <a name="InstallTheTools"></a>Nainstalujte nástroje  
 Instalační program sady Visual Studio 2015 zahrnuje možnost nainstalovat Visual C++ pro vývoj mobilních řešení pro různé platformy. Tím se nainstaluje požadované C++ jazykové nástroje, šablony a součásti pro Visual Studio, RSZ a Clang modulové potřebná pro Android sestavení a ladění a součásti pro komunikaci s počítačem Mac pro vývoj pro iOS. Nainstaluje taky všechny nástroje třetích stran a software development Kit, které jsou potřebné k podpoře vývoj aplikace pro Android a iOS. Většina těchto nástrojů jiných výrobců jsou open-source softwaru, které jsou potřebné pro podporu platformu Android.  
  
-   Android Kit nativní vývoj (NDK) je potřeba vytvořit kódu C++, která je cílena platformu Android.  
  
-   Android SDK, Apache Ant a Java SE Development Kit jsou vyžadovány pro proces Android sestavení.  
  
-   Microsoft Visual Studio Emulator for Android je volitelné vysoce výkonné emulátoru užitečné pro testování a ladění kódu.  
  
#### <a name="to-install-visual-c-for-cross-platform-mobile-development-and-the-third-party-tools"></a>Instalace Visual C++ pro vývoj mobilních řešení pro různé platformy a nástroje třetích stran  
  
1.  Spusťte instalační program sady Visual Studio 2015, který jste stáhli následující odkaz v [získat nástroje](#GetTheTools). Chcete-li nainstalovat volitelné součásti, zvolte **vlastní** jako typ instalace. Zvolte **Další** vyberte volitelné součásti k instalaci.  
  
2.  V vyberte funkce, rozbalte položku **vývoj pro různé platformy Mobile** a zkontrolujte **Visual C++ vývoj mobilních řešení**.  
  
     ![Vyberte Visual C & č. 43; & č. 43; Mobilní vývoj](../cross-platform/media/cppmdd_install_vcmdd.png "CPPMDD_Install_VCMDD")  
  
     Ve výchozím nastavení, když vyberete **Visual C++ vývoj mobilních řešení**, **programovací jazyky** je možnost nastavena k instalaci **Visual C++**a **běžné nástroje pro a Software Development Kit** jsou nastavené možnosti instalace požadovaných součástí třetích stran. Pokud je potřebujete, můžete zvolit další součásti. Ve výchozím nastavení **Microsoft Visual Studio Emulator for Android** , vybere se také. Neaktivní v seznamu se zobrazí součásti, které jsou již nainstalovány.  
  
     K sestavení univerzální aplikace pro Windows a jejich sdílení v kódu mezi nimi a vašich projektů Android a iOS **vyberte funkce**, rozbalte položku **Windows a vývoj webů** a zkontrolujte **univerzální aplikace pro Windows Nástroje pro vývoj**. Pokud nemáte v úmyslu vytvořit univerzální aplikace pro Windows, můžete přeskočit tuto možnost.  
  
     Zvolte **Další** pokračujte.  
  
3.  Komponenty třetích stran mají své vlastní licenční podmínky. Licenční podmínky můžete zobrazit výběrem **licenční podmínky** odkaz vedle jednotlivých součástí. Zvolte **nainstalovat** přidejte součásti a instalace sady Visual Studio a Visual C++ pro vývoj mobilních řešení pro různé platformy.  
  
4.  Po dokončení instalace ukončete instalační program a potom restartujte počítač. Některé akce instalace pro komponenty jiných výrobců se projeví až po restartování počítače.  
  
    > [!IMPORTANT]
    >  Je nutné restartovat a ujistěte se, že se vše správně nainstalovalo.  
  
     Pokud emulátor Microsoft Visual Studio pro Android součásti se nepodařilo nainstalovat, váš počítač nemusí mít Hyper-V povolena. Použití **Windows zapnout nebo vypnout funkce** aplikace ovládacích panelů povolit technologie Hyper-V, a poté znovu spusťte instalační program sady Visual Studio.  
  
    > [!NOTE]
    >  Pokud váš počítač nebo vaši verzi systému Windows nepodporuje technologie Hyper-V, nebudete moct používat emulátor sady Microsoft Visual Studio pro Android součást. Domů edice systému Windows nezahrnuje podpory technologie Hyper-V.  
  
5.  Otevřete Visual Studio. Pokud je při prvním spuštění sady Visual Studio, může trvat nějakou dobu ke konfiguraci a přihlaste se. Když je připraven, v sadě Visual Studio **nástroje** nabídce vyberte možnost **rozšíření a aktualizace**, **aktualizace**. Pokud že Visual Studio aktualizace k dispozici pro Visual C++ pro vývoj mobilních řešení pro různé platformy, nebo pro Microsoft Visual Studio Emulator for Android, je nainstalujte.  
  
##  <a name="InstallForiOS"></a>Instalace nástrojů pro iOS  
 Visual C++ pro vývoj mobilních řešení pro různé platformy můžete použít k úpravám, ladění a nasazení iOS kódu simulátoru iOS nebo zařízení s iOS, ale kvůli licenční omezení, kód musí být vytvořen vzdáleně v počítačích Mac. Sestavení a spuštění aplikace pro iOS pomocí sady Visual Studio, musíte nastavit a nakonfigurovat vzdáleného agenta na vaše Mac. Podrobné pokyny k instalaci, požadavky a možnosti konfigurace najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Pokud nejsou vytvářet pro iOS, můžete tento krok přeskočit.  
  
##  <a name="ThirdParty"></a>Instalace nebo ručně aktualizovat závislosti  
 Pokud se rozhodnete nainstalovat jeden nebo více závislostí třetích stran pomocí instalačního programu sady Visual Studio, když instalujete Visual C++ vývoj mobilních řešení možnost, můžete je nainstalovat později pomocí kroků v [nainstalovat nástroje](#InstallTheTools). Můžete také nainstalovat nebo je aktualizovat nezávisle na Visual Studio.  
  
> [!CAUTION]
>  Závislosti můžete nainstalovat v libovolném pořadí, s výjimkou Java. Musíte nainstalovat a nakonfigurovat sadu JDK, před instalací sady SDK pro Android.  
  
 Přečtěte si následující informace a použijte tyto odkazy ruční instalace závislosti.  
  
-   [Java SE Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)  
  
     Ve výchozím nastavení převede instalační program nástroje Java v C:\Program Files (x86) \Java.  
  
-   [Sady SDK pro Android](https://developer.android.com/sdk/index.html#Other)  
  
     Během instalace aktualizace rozhraní API podle doporučení. Ujistěte se, že aspoň je nainstalována sada SDK pro Android 5.0 typu Lupa (API úrovně 21). Ve výchozím nastavení převede instalační program sady SDK pro Android v C:\Program Files (x86) \Android\android-sdk.  
  
     SDK Manager aplikaci můžete spustit v adresáři sady SDK pro Android znovu a aktualizovat sadu SDK a instalaci volitelných nástrojů a další úrovně rozhraní API. Aktualizace se pravděpodobně nepodaří nainstalovat, pokud nechcete použít **spustit jako správce** aplikace SDK Manager spustit. Pokud máte potíže s vytváření aplikace pro Android, zkontrolujte SDK Manager aktualizace vašeho nainstalované sady SDK.  
  
     Používat některé z Android emulátorů, které jsou součástí sady SDK pro Android, musíte nainstalovat volitelné Intel HAXM ovladače. Možná budete muset odebrat funkce Hyper-V ze systému Windows k instalaci ovladačů Intel HAXM úspěšně. Je nutné obnovit funkce Hyper-V použít emulátorů Windows Phone a emulátor sady Microsoft Visual Studio pro Android.  
  
-   [Android NDK](https://developer.android.com/tools/sdk/ndk/index.html)  
  
     Ve výchozím nastavení instalační program převádí na C:\ProgramData\Microsoft\AndroidNDK Android NDK. Můžete stáhnout a nainstalovat Android NDK znovu, aby NDK instalace aktualizace.  
  
-   [Apache Ant](http://ant.apache.org/bindownload.cgi)  
  
     Ve výchozím nastavení instalační program vloží Apache Ant C:\Program Files (x86) \Microsoft Visual Studio 14.0\Apps.  
  
-   [Emulátor Microsoft Visual Studio pro Android](http://go.microsoft.com/fwlink/p/?LinkId=536390)  
  
     Můžete nainstalovat a aktualizovat emulátor sady Microsoft Visual Studio pro Android z Galerie Visual Studio.  
  
 Ve většině případů lze zjistit sady Visual Studio konfigurace pro software třetích stran, které jste nainstalovali a udržuje cesty instalace v proměnných prostředí interní. Můžete přepsat výchozí cesty těchto nástrojů pro vývoj pro různé platformy v integrovaném vývojovém prostředí sady Visual Studio.  
  
#### <a name="to-set-the-paths-for-third-party-tools"></a>Chcete-li nastavit cesty pro nástroje třetích stran  
  
1.  V řádku nabídek Visual Studio, vyberte **nástroje**, **možnosti**.  
  
2.  V **možnosti** dialogové okno, rozbalte seznam **křížové platformy**, **C++**a vyberte **Android**.  
  
     ![Nástroj pro Android cesta možnosti](../cross-platform/media/cppmdd_options_android.PNG "CPPMDD_Options_Android")  
  
3.  Chcete-li změnit tuto cestu používají nástroj, zaškrtněte políčko vedle cestu a upravit cesta ke složce, do textového pole. Můžete také použít tlačítko pro procházení (**...** ) Chcete-li otevřít **vyberte umístění** dialogové okno a vyberte složku.  
  
4.  Zvolte **OK** uložit vlastní nástroj umístění složek.  
  
## <a name="see-also"></a>Viz také  
 [Instalace a konfigurace nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md)   
 [Visual C++ a platformy Mobile](https://www.visualstudio.com/explore/cplusplus-mdd-vs.aspx)