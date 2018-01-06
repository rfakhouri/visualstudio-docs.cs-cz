---
title: "Sestavení aplikace OpenGL ES pro Android a iOS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 76a67886-df57-4a81-accb-2e3c2eaf607b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: xplat-cplusplus
ms.openlocfilehash: 6378826a090b05a681a4808573eefd95899b9f6a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="build-an-opengl-es-application-on-android-and-ios"></a>Sestavení aplikace OpenGL ES pro Android a iOS
Když instalujete Visual C++ pro vývoj mobilních řešení pro různé platformy možnost, můžete vytvořit řešení sady Visual Studio a projekty pro aplikace pro iOS a Android aplikace, které sdílejí společný kód. Toto téma vás provede řešení šablonu, která vytvoří aplikace pro jednoduché iOS a Android nativní aktivity aplikace. Aplikací mít C++ – kód společné používané OpenGL ES zobrazíte stejné animovaný rotační datové krychle na každé platformě. ES OpenGL (OpenGL pro Embedded Systems nebo GLES) je 2D a 3D grafické rozhraní API, která je podporována v mnoho mobilních zařízení.  
  
 [Požadavky](#req)   
 [Vytvoření nového projektu OpenGLES aplikace](#Create)   
 [Sestavení a spuštění aplikace pro Android](#BuildAndroid)   
 [Sestavení a spuštění aplikace pro iOS](#BuildIOS)   
 [Přizpůsobení aplikací](#Customize)  
  
##  <a name="req"></a>Požadavky  
 Před vytvořením aplikace OpenGL ES pro iOS a Android, musí se zkontrolujte, zda že jste splněny všechny požadavky na systém. Je nutné nainstalovat Visual C++ pro možnost vývoj mobilních řešení pro různé platformy ve Visual Studiu 2015. Ujistěte se, že požadované nástroje třetích stran a sady SDK jsou součástí instalace a nainstalovanou emulátor sady Visual Studio pro Android. Další informace a podrobné pokyny najdete v tématu [nainstalovat Visual C++ pro vývoj mobilních řešení pro různé platformy](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Pro vytvoření a testování aplikace pro iOS, budete potřebovat Mac počítače, nastavení podle pokynů pro instalaci. Další informace o tom, jak nastavit pro vývoj pro iOS najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md)  
  
##  <a name="Create"></a>Vytvoření nového projektu OpenGLES aplikace  
 V tomto kurzu nejprve vytvořit nový projekt aplikace OpenGL ES a následně vytvořit a spustit výchozí aplikace v emulátor sady Visual Studio pro Android. Vedle vytváření aplikace pro iOS a spusťte aplikaci v simulátoru iOS.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Otevřete Visual Studio. Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V **nový projekt** dialogovém **šablony**, zvolte **Visual C++**, **křížové platformy**a potom vyberte  **OpenGLES aplikace (Android, iOS)** šablony.  
  
3.  Zadejte název jako aplikace `MyOpenGLESApp`a potom zvolte **OK**.  
  
     ![Nový projekt aplikace OpenGLES](../cross-platform/media/cppmdd_opengles_newproj.PNG "CPPMDD_OpenGLES_NewProj")  
  
     Visual Studio vytvoří nové řešení a otevře Průzkumníka řešení.  
  
     ![V Průzkumníku řešení MyOpenGLESApp](../cross-platform/media/cppmdd_opengles_solexpl.PNG "CPPMDD_OpenGLES_SolExpl")  
  
 Nové řešení aplikace OpenGL ES zahrnuje tři projekty knihovny a dva projekty aplikací. Složka knihovny zahrnuje projektu sdíleného kódu a dva projekty specifických pro platformy, které odkazují sdíleného kódu:  
  
-   **MyOpenGLESApp.Android.NativeActivity** obsahuje odkazy a spojovací kód, který implementuje aplikace jako nativní aktivita v systému Android. Implementace vstupních bodů z kódu spojovací jsou main.cpp, která zahrnuje společný kód sdílený v MyOpenGLESApp.Shared. Předkompilované hlavičky jsou pch.h. Tento projekt aplikace nativní aktivity zkompilován soubor sdílené knihovny (.so), který je převzata MyOpenGLESApp.Android.Packaging projektu.  
  
-   **MyOpenGLESApp.iOS.StaticLibrary** vytvoří soubor iOS statické knihovny (.a), který obsahuje kód sdílené v MyOpenGLESApp.Shared. Je propojen aplikace vytvořené MyOpenGLESApp.iOS.Application projektu.  
  
-   **MyOpenGLESApp.Shared** obsahuje sdílené kód, který funguje napříč platformami. Makra preprocesoru používá pro Podmíněná kompilace kódu pro konkrétní platformu. Kód sdílený je převzata odkazem projektu v MyOpenGLESApp.Android.NativeActivity a MyOpenGLESApp.iOS.StaticLibrary.  
  
 Řešení obsahuje dva projekty k vytváření aplikací pro platformy Android a iOS:  
  
-   **MyOpenGLESApp.Android.Packaging** vytvoří soubor .apk pro nasazení na emulátoru nebo zařízení s Androidem. Tato položka obsahuje prostředků a kde nastavíte vlastnosti manifestu souboru AndroidManifest.xml. Obsahuje taky build.xml soubor, který řídí procesu sestavení Ant. Ho jako projekt po spuštění ve výchozím nastavení, takže ho můžete nasadit a spustit přímo ze sady Visual Studio.  
  
-   **MyOpenGLESApp.iOS.Application** obsahuje prostředky a kód jazyka Objective-C spojovací k vytvoření aplikace pro iOS, který odkazuje na statické knihovny kódu C++ v MyOpenGLESApp.iOS.StaticLibrary. Tento projekt vytvoří balíček sestavení, který se přenese do počítače Mac pomocí sady Visual Studio a vzdáleného agenta. Při sestavování projektu sady Visual Studio odešle soubory a příkazy pro sestavení a nasazení aplikace na Mac.  
  
##  <a name="BuildAndroid"></a>Sestavení a spuštění aplikace pro Android  
 Řešení vytvořených šablonou nastaví jako výchozí projekt aplikace pro Android.  Můžete sestavit a spustit tuto aplikaci a ověření instalace a nastavení. Pro počáteční test spuštění aplikace na jeden z profilů zařízení nainstalovat pomocí emulátor sady Visual Studio pro Android. Pokud dáváte přednost k testování aplikace na jiný cíl, můžete načíst cílový emulátoru nebo připojení zařízení k počítači.  
  
#### <a name="to-build-and-run-the-android-native-activity-app"></a>Sestavení a spuštění aplikace Android nativní aktivity  
  
1.  Pokud již není vybrána, vyberte **x86** z **platformy řešení** rozevíracího seznamu.  
  
     ![Nastavte platforma řešení na x86](../cross-platform/media/cppmdd_opengles_solutionplat.png "CPPMDD_OpenGLES_SolutionPlat")  
  
     Pomocí x86 cíle Android emulátor pro Windows. Pokud cílíte na zařízení, zvolte platforma řešení založená na procesor zařízení. Pokud **platformy řešení** seznamu není, zvolte možnost **platformy řešení** z **tlačítka Přidat nebo odebrat** seznamu a potom vyberte vaši platformu.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídky pro MyOpenGLESApp.Android.Packaging projekt a zvolte **sestavení**.  
  
     ![Sestavení projektu Android balení](../cross-platform/media/cppmdd_opengles_andbuild.png "CPPMDD_OpenGLES_AndBuild")  
  
     Ve výstupním okně zobrazí výstup procesu sestavení pro systém Android sdílené knihovny a aplikace pro Android.  
  
     ![Sestavení výstup pro Android projekty](../cross-platform/media/cppmdd_opengles_andoutput.png "CPPMDD_OpenGLES_AndOutput")  
  
3.  Vyberte jednu z emulátoru VS telefon se systémem Android (x86) profily jako cíl vaše nasazení.  
  
     ![Vyberte cíl nasazení](../cross-platform/media/cppmdd_opengles_pickemulator.png "CPPMDD_OpenGLES_PickEmulator")  
  
     Pokud jste nainstalovali další emulátorů nebo připojené zařízení s Androidem, můžete je v rozevíracím seznamu cíl nasazení. Pokud chcete spustit aplikaci, musí odpovídat platformou integrované řešení platformu cílového zařízení.  
  
4.  Stisknutím klávesy F5 spusťte ladění nebo Shift + F5 a spusťte bez ladění.  
  
     Visual Studio spustí se emulátor, který přebírá několik sekund se načíst a nasadíte tak svůj kód. Zde je, jak se aplikace se zobrazí v emulátor sady Visual Studio pro Android.  
  
     ![Aplikace spuštěná v emulátoru Android](../cross-platform/media/cppmdd_opengles_andemulator.png "CPPMDD_OpenGLES_AndEmulator")  
  
     Po zahájení aplikace, můžete nastavit zarážky a používat ladicí program ke kroku prostřednictvím kódu, zkontrolujte místní hodnoty a podívejte se na hodnoty.  
  
5.  Stiskněte Shift + F5 ukončete ladění.  
  
     Emulátor je samostatný proces, který stále běží. Můžete upravit, kompilace a nasazení kódu do stejné emulátoru vícekrát. Aplikace se zobrazí v kolekci aplikaci v emulátoru a jej lze spustit z ní přímo.  
  
 Vygenerovaný Android aktivity nativní aplikaci a knihovny projektů put C++ sdíleného kódu v dynamické knihovně, která obsahuje "spojovací" kód pro rozhraní s platformu Android. To znamená, že většinu kódu aplikace v knihovně, a manifestu, prostředky a pokyny pro sestavení jsou v balení projektu. Kód sdílený je volána z main.cpp v NativeActivity projektu. Další informace o tom, jak program aktivitu nativní Android, najdete v části Android NDK vývojáře [koncepty](https://developer.android.com/ndk/guides/concepts.html) stránky.  
  
 Visual Studio vytvoří pomocí Android NDK, který používá jako sada nástrojů platformy Clang projektů Android nativní aktivity. Visual Studio mapuje vlastnosti v projektu NativeActivity přepínače příkazového řádku a možnosti, které slouží ke kompilaci, propojit a ladění na cílové platformy. Podrobnosti, otevřete **stránky vlastností** dialogové okno pro projekt MyOpenGLESApp.Android.NativeActivity. Další informace o parametrech příkazového řádku najdete v tématu [Clang kompilátoru uživatelské příručce](http://clang.llvm.org/docs/UsersManual.html).  
  
##  <a name="BuildIOS"></a>Sestavení a spuštění aplikace pro iOS  
 Projekt aplikace pro iOS je vytvořena a upravit v sadě Visual Studio, ale kvůli licenční omezení, musí být vytvořené a nasazené z macu. Visual Studio komunikuje s vzdáleného agenta spuštěného na Mac k přenosu souborů projektu a spuštění sestavení, nasazení a ladění příkazy. Musíte nastavit a nakonfigurovat Mac a Visual Studio pro komunikaci, než můžete vytvořit aplikaci pro iOS. Podrobné pokyny najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Jakmile je spuštěna vzdáleného agenta a Visual Studio je spárován s počítači Mac, můžete sestavit a spustit aplikaci pro iOS k ověření instalace a nastavení.  
  
#### <a name="to-build-and-run-the-ios-app"></a>Sestavení a spuštění aplikace pro iOS  
  
1.  Ověřte, zda je spuštěna vzdáleného agenta na počítači Mac a sadou Visual Studio je spárováno s vzdáleného agenta. Chcete-li spustit vzdáleného agenta, otevřete okno terminálu aplikace a zadejte `vcremote`. Další informace najdete v tématu [konfigurace vzdáleného agenta v sadě Visual Studio](../cross-platform/install-and-configure-tools-to-build-using-ios.md#ConfigureVS).  
  
     ![Okno terminálu Mac systémem vcremote](../cross-platform/media/cppmdd_common_vcremote.png "CPPMDD_common_vcremote")  
  
2.  Pokud již není vybrána, vyberte **x86** z **platformy řešení** rozevíracího seznamu.  
  
     ![Nastavte platforma řešení na x86](../cross-platform/media/cppmdd_opengles_solutionplat.png "CPPMDD_OpenGLES_SolutionPlat")  
  
     Pomocí x86 cíle simulátoru iOS. Pokud cílíte na zařízení s iOS, zvolte platforma řešení založená na procesor zařízení (obvykle procesor ARM). Pokud **platformy řešení** seznamu není, zvolte možnost **platformy řešení** z **tlačítka Přidat nebo odebrat** seznamu a potom vyberte vaši platformu.  
  
3.  V Průzkumníku řešení otevřete místní nabídku pro MyOpenGLESApp.iOS.Application projekt a zvolte **sestavení**.  
  
     ![Sestavení projektu aplikace iOS](../cross-platform/media/cppmdd_opengles_iosbuild.png "CPPMDD_OpenGLES_iOSBuild")  
  
     Ve výstupním okně zobrazí výstup procesu sestavení se statickou knihovnou iOS a aplikaci pro iOS. V systému Mac okno terminálu spuštění vzdáleného agenta ukazuje příkazu a soubor přenést aktivity.  
  
     V počítači Mac, můžete být vyzváni v přijmout žádost o podepsání kódu. Zvolte povolit, pokračujte.  
  
4.  Zvolte **simulátoru iOS** na panelu nástrojů a spusťte aplikaci v simulátoru iOS na vaše Mac. Může trvat chvilku simulátoru. Možná budete muset uvést simulátoru na popředí na počítači Mac zobrazíte její výstup.  
  
     ![Aplikaci spuštěnou na simulátoru iOS](../cross-platform/media/cppmdd_opengles_iossimulator.png "CPPMDD_OpenGLES_iOSSimulator")  
  
     Po zahájení aplikace, můžete nastavit zarážky a pomocí ladicího programu sady Visual Studio prohlédnout místní hodnoty, najdete v zásobníku volání a podívejte se na hodnoty.  
  
     ![Ladicí program na zarážka v aplikaci pro iOS](../cross-platform/media/cppmdd_opengles_iosdebug.png "CPPMDD_OpenGLES_iOSDebug")  
  
5.  Stiskněte Shift + F5 ukončete ladění.  
  
     IOS simulátoru je samostatný proces, který pokračuje v činnosti na vaše Mac. Můžete upravit, kompilace a nasadíte tak svůj kód vícekrát na stejnou instanci simulátoru iOS. Svůj kód můžete také spustit přímo v simulátoru po jeho nasazení.  
  
 Vygenerovaný iOS aplikace a knihovny projekty uveďte kódu C++ v statickou knihovnu, která implementuje pouze kód, sdílené. Většinu kódu aplikace je v projektu aplikace. Volání kódu sdílené knihovny v tomto projektu šablony jsou vytvářeny v souboru GameViewController.m. Pokud chcete vytvořit aplikaci s iOS, Visual Studio použije sada nástrojů platformy Xcode, který vyžaduje komunikaci se vzdáleným klientem, který běží na macu.  
  
 Visual Studio přenese soubory projektu a odešle příkazy ke vzdálenému klientovi k sestavení aplikace pomocí Xcode. Vzdálený klient odešle sestavení informace o stavu zpět do Visual Studio. Když aplikace má vytvořen úspěšně, můžete odeslat příkazy ke spouštění a ladění aplikace Visual Studio. V ladicím programu sady Visual Studio řídí spuštěné v simulátoru iOS běžícím v počítači Mac, nebo na zařízení s iOS připojené aplikace. Visual Studio mapuje vlastnosti v projektu StaticLibrary přepínače příkazového řádku a možnosti, které se používají k vytváření, propojení a ladění na cílové platformy iOS. Podrobnosti kompilátoru příkazového řádku, otevřete **stránky vlastností** dialogové okno pro projekt MyOpenGLESApp.iOS.StaticLibrary.  
  
##  <a name="Customize"></a>Přizpůsobení aplikací  
 Můžete upravit sdíleného kódu C++ přidat nebo změnit běžné funkce. Je nutné změnit volání do sdíleného kódu v projektech MyOpenGLESApp.Android.NativeActivity a MyOpenGLESApp.iOS.Application tak, aby odpovídaly. Makra preprocesoru můžete použít k určení specifických pro platformy oddíly v společný kód. Makro preprocesoru `__ANDROID__` je předdefinovaná při vytváření pro Android. Makro preprocesoru `__APPLE__` je předdefinovaná při sestavení pro iOS.  
  
 Zobrazit IntelliSense pro konkrétní projekt platformu, vyberte projekt v rozevírací nabídce kontextu přepínači na navigačním panelu v horní části okna editoru.  
  
 ![Projekt kontextu přepínači rozevírací seznam v editoru](../cross-platform/media/cppmdd_opengles_contextswitcher.png "CPPMDD_OpenGLES_ContextSwitcher")  
  
 Problémy IntelliSense v aktuálním projektu jsou označené červenou vlnovkou. Problémy v jiné projekty jsou označené fialové vlnovka. Ve výchozím nastavení Visual Studio nepodporuje kód zabarvení ani IntelliSense pro soubory Java nebo jazyka Objective-C. Můžete však stále upravit zdrojové soubory a změnit prostředky, které chcete nastavit název aplikace, ikona a další podrobnosti implementace.