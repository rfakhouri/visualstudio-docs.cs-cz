---
title: Vytvoření aplikace OpenGL ES na Androidu a iOS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 05/16/2019
ms.technology: vs-ide-mobile
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76a67886-df57-4a81-accb-2e3c2eaf607b
author: corob-msft
ms.author: corob
manager: jillfra
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: aa8ffe308f8a1181ed18af52ba7537c46007de94
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317654"
---
# <a name="build-an-opengl-es-application-on-android-and-ios"></a>Vytvoření aplikace OpenGL ES na Androidu a iOS

Můžete vytvářet řešení sady Visual Studio a projekty pro aplikace pro iOS a aplikace pro Android, které sdílejí společný kód. Tento článek vás provede šablonu řešení, která vytvoří jednoduchý iOS aplikace i aplikace Android Native Activity. Aplikace mají kódu jazyka C++ společné, které využívá OpenGL ES zobrazíte stejné animovaný otáčení datové krychle na každé platformě. OpenGL ES (OpenGL pro vložené systémy nebo GLES) je 2D a 3D grafice rozhraní API, která je podporována v mnoha mobilních zařízení.

## <a name="requirements"></a>Požadavky

Před vytvořením aplikace OpenGL ES pro iOS a Android, ujistěte se, že jste splnili všechny požadavky na systém. Pokud jste tak dosud neučinili, nainstalujte vývoj mobilních aplikací pomocí C++ úlohy v instalačním programu sady Visual Studio. K sestavení pro iOS, zahrnout volitelné C++ nástroje pro vývoj pro iOS. K sestavení pro Android, nainstalujte C++ nástroje pro vývoj pro Android a požadovanými nástroji třetích stran: Sada Android NDK, Apache Ant, emulátor Google Android a Intel Hardware Accelerated správce spuštění. V dalším kroku nakonfigurujte Intel HAXM a emulátor Androidu pro spuštění ve vašem systému. Další informace a podrobné pokyny najdete v tématu [instalaci Visual C++ pro vývoj mobilních řešení napříč platformami](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Pokud chcete sestavovat a testovat aplikace pro iOS, budete potřebovat počítač Mac počítačů, nastavení podle pokynů k instalaci. Další informace o tom, jak nastavit pro vývoj pro iOS najdete v tématu [instalace a konfigurace nástroje potřebné k vytváření pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md)

## <a name="create-a-new-opengles-application-project"></a>Vytvoření nového projektu aplikace OpenGLES

V tomto kurzu nejprve vytvořte nový projekt aplikace OpenGL ES a následně vytvořit a spustit výchozí aplikaci v emulátoru Visual Studia pro Android. Dále vytvořte aplikaci pro iOS a spuštění aplikace na zařízení s Iosem.

1. V sadě Visual Studio, zvolte **souboru** > **nový** > **projektu**.

1. V **nový projekt** dialogovém okně **šablony**, zvolte **Visual C++**  > **různé platformy**a klikněte na tlačítko **Aplikace OpenGLES (Android, iOS)** šablony.

1. Dejte aplikaci s názvem jako `MyOpenGLESApp`a klikněte na tlačítko **OK**.

   ![Nový projekt aplikace OpenGLES](../cross-platform/media/cppmdd_opengles_newproj.PNG "CPPMDD_OpenGLES_NewProj")

   Visual Studio vytvoří nové řešení a otevře se Průzkumník řešení.

   ![V Průzkumníku řešení MyOpenGLESApp](../cross-platform/media/cppmdd_opengles_solexpl.PNG "CPPMDD_OpenGLES_SolExpl")

   Nové řešení aplikace OpenGL ES obsahuje tři projekty knihovny a dva projekty aplikací. Složka knihovny obsahuje dva projekty specifické pro platformu, které odkazují na sdílený kód a projekt sdíleného kódu:

- `MyOpenGLESApp.Android.NativeActivity` obsahuje odkazy na a spojovací kód, který implementuje vaši aplikaci jako nativní aktivita v Androidu. Vstupní body z spojovacího kódu jsou implementovány v *main.cpp*, což zahrnuje společný kód sdílený v `MyOpenGLESApp.Shared`. Předkompilované hlavičky jsou v *soubor pch.h*. Tento projekt aplikace Nativeactivity je zkompilován do sdílené knihovny ( *.so*) soubor, který převezme `MyOpenGLESApp.Android.Packaging` projektu.

- `MyOpenGLESApp.iOS.StaticLibrary` Vytvoří statickou knihovnu iOS ( *.a*) obsahující sdílený kód v `MyOpenGLESApp.Shared`. Je propojené s aplikací vytvořené `MyOpenGLESApp.iOS.Application` projektu.

- `MyOpenGLESApp.Shared` obsahuje sdílený kód, který funguje napříč platformami. Makra preprocesoru se používá pro podmíněnou kompilaci kódu specifické pro platformu. Sdílený kód převezme odkaz na projekt v obou `MyOpenGLESApp.Android.NativeActivity` a `MyOpenGLESApp.iOS.StaticLibrary`.

Řešení obsahuje dva projekty k sestavení aplikací pro platformy Android a iOS:

- `MyOpenGLESApp.Android.Packaging` vytvoří *.apk* souboru pro nasazení na emulátoru nebo zařízení s Androidem. Tento soubor obsahuje prostředky a souboru AndroidManifest.xml, kde nastavíte vlastnosti manifestu. Obsahuje taky *build.xml* soubor, který určuje, Ant procesu sestavení. Ho jako spouštěný projekt ve výchozím nastavení, takže je možné nasadit a spustit přímo ze sady Visual Studio.

- **MyOpenGLESApp.iOS.Application** obsahuje prostředky a Objective-C spojovací kód k vytvoření aplikace pro iOS, která odkazuje na statickou knihovnu kódu C++ v `MyOpenGLESApp.iOS.StaticLibrary`. Tento projekt vytvoří balíček sestavení, který bude převeden na počítači Mac pomocí sady Visual Studio a vzdáleného agenta. Při sestavování tohoto projektu sady Visual Studio odešle soubory a příkazy k vytvoření a nasazení vaší aplikace na počítači Mac.

## <a name="build-and-run-the-android-app"></a>Sestavte a spusťte aplikaci pro Android

Řešení vytvořených šablonou nastaví jako výchozí projekt aplikace pro Android.  Můžete sestavit a spustit tuto aplikaci k ověření instalace a nastavení. Pro počáteční testování spusťte aplikaci na jeden z profilů zařízení, nainstalovat emulátor pro Android. Pokud chcete testovat svou aplikaci na jiný cíl, můžete načíst cíl emulátor nebo připojte zařízení k počítači.

### <a name="to-build-and-run-the-android-native-activity-app"></a>Sestavení a spuštění aplikace Android Native Activity

1. Pokud ještě není vybraná, zvolte **x86** z **platformy řešení** rozevíracího seznamu.

   ![Nastavte platformu řešení na x86](../cross-platform/media/cppmdd_opengles_solutionplat.png "CPPMDD_OpenGLES_SolutionPlat")

   Pomocí x86 zaměřit na emulátor. Pro cíl na nějaké zařízení, zvolte platformu řešení založené na procesoru zařízení. Pokud **platformy řešení** seznamu se nezobrazí, zvolte **platformy řešení** z **přidat nebo odebrat tlačítka** seznamu a pak zvolte vaši platformu.

1. V **Průzkumníka řešení**, otevřete místní nabídku pro `MyOpenGLESApp.Android.Packaging` projektu a klikněte na tlačítko **sestavení**.

   ![Vytvoření balíčků pro Android projektu](../cross-platform/media/cppmdd_opengles_andbuild.png "CPPMDD_OpenGLES_AndBuild")

   V okně výstupu zobrazí výstup z procesu sestavení pro Android sdílené knihovny a aplikace pro Android.

   ![Výstup sestavení pro projekty pro Android](../cross-platform/media/cppmdd_opengles_andoutput.png "CPPMDD_OpenGLES_AndOutput")

1. Zvolte jeden z profilů emulované zařízení s Androidem jako cíl nasazení.

   ![Zvolte cíl nasazení](../cross-platform/media/cppmdd_opengles_pickemulator.png "CPPMDD_OpenGLES_PickEmulator")

   Pokud jste nainstalovali jiné emulátory nebo připojené zařízení s Androidem, můžete je v rozevíracím seznamu cíl nasazení. Spusťte aplikaci, musí odpovídat sestavené platforma řešení platformě cílového zařízení.

1. Stisknutím klávesy F5 spusťte ladění nebo Shift + F5 spustit bez ladění.

   Visual Studio spustí se emulátor, který trvá několik sekund se má načíst a nasaďte svůj kód. Zde je, jak se aplikace objeví v emulátoru:

   ![Aplikace spuštěné v emulátoru Androidu](../cross-platform/media/cppmdd_opengles_andemulator.png "CPPMDD_OpenGLES_AndEmulator")

   Po zahájení vaší aplikace můžete nastavit zarážky a ladicího programu můžete krokovat kód, prozkoumat místní hodnoty a podívejte se na hodnoty.

1. Stisknutím klávesy **Shift**+**F5** chcete zastavit ladění.

   Emulátor je samostatný proces, který zůstane spuštěný. Můžete upravit, zkompilujte a nasaďte svůj kód do stejné emulátor více než jednou. Vaše aplikace se zobrazí v kolekci aplikaci v emulátoru a ji můžete spustit z něj přímo.

   Vygenerovaný Android Nativeactivity aplikace a knihovny projektů vložit jazyka C++ sdíleného kódu ve dynamická knihovna, která obsahuje kód "spojovací" rozhraní s platformy Android. Většinu kódu aplikace je v knihovně a manifest, prostředky a pokyny pro sestavení jsou do balícího projektu. Sdílený kód je volána z main.cpp v projektu NativeActivity. Další informace o tom, jak aplikace Nativeactivity pro Android, najdete v části Android NDK pro vývojáře [koncepty](https://developer.android.com/ndk/guides/concepts.html) stránky.

   Sada Visual Studio sestavuje projekty Nativeactivity pro Android pomocí Android NDK, který používá jako sada nástrojů platformy Clang. Visual Studio mapuje vlastností v projektu NativeActivity možnosti používá ke kompilaci, propojení a ladění na cílovou platformu. Podrobnosti, otevřete **stránky vlastností** dialogové okno pro MyOpenGLESApp.Android.NativeActivity projektu. Další informace o parametrech příkazového řádku najdete v tématu [Clang kompilátoru uživatelské příručce](http://clang.llvm.org/docs/UsersManual.html).

## <a name="build-and-run-the-ios-app-on-an-ios-device"></a>Sestavte a spusťte aplikaci pro iOS na zařízení s iOS

Projekt aplikace pro iOS je vytvořena a upravovat v sadě Visual Studio, ale z důvodu licenčních omezení, musí být vytvořené a nasazené z macu. Komunikuje se službou Vzdálená agenta spuštěného na počítači Mac k přenosu souborů projektu a spuštění sestavení, nasazení a ladění příkazů sady Visual Studio. Nastavení a konfigurace Mac a Visual Studio ke komunikaci před sestavením aplikace pro iOS. Podrobné pokyny najdete v tématu [instalace a konfigurace nástroje potřebné k vytváření pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Jakmile se vzdálený agent běží na počítači Mac a spárovaná s aplikací Visual Studio, můžete sestavit a spustit aplikaci pro iOS k ověření instalace a nastavení.

Pokud chcete nasadit aplikace pro iOS zařízení s Iosem, musíte také nastavit automatické podepisování v Xcode na macu Automatické podepisování automaticky spravuje podepisování aplikací a vytvoří zřizovacího profilu k podepsání a nové sestavení aplikace.

### <a name="to-set-up-automatic-signing-on-xcode"></a>Nastavení automatické podepisování v Xcode

1. Pokud jste tak dosud neučinili, nainstalujte [Xcode](https://developer.apple.com/xcode/downloads/) verze 10.2.1 nebo novějším na vašem počítači Mac.

1. Otevřete aplikaci Xcode na vašem počítači Mac.

1. Vytvořte nový **jediné zobrazení aplikace** projektu Xcode. Vyplňte požadovaná pole při vytváření projektu. Hodnoty mohou být libovolného, protože projektu slouží pouze k vytvoření zřizovacího profilu, který se později používá k podepsání a nové sestavení aplikace.

1. Přidat Apple ID, které je zaregistrované v [Apple Developer Program](https://developer.apple.com/programs/) účet pro Xcode. Vaše Apple ID, které slouží jako podpisové identity k podepisování aplikací. Chcete-li přidat podpisové identity v Xcode, otevřete **Xcode** nabídku a zvolte **Předvolby**. Vyberte **účty** a klikněte na tlačítko Přidat (+) a přidejte své Apple ID. Podrobné pokyny najdete v tématu [přidal váš účet Apple ID, které](https://help.apple.com/xcode/mac/current/#/devaf282080a).

1. Z projektu Xcode "Obecné" nastavení, změňte hodnotu vlastnosti **identifikátor sady prostředků** k `com.<NameOfVSProject>`, kde `<NameOfVSProject>` se stejným názvem jako projekt řešení sady Visual Studio jste vytvořili. Například, pokud jste vytvořili projekt s názvem `MyOpenGLESApp` v sadě Visual Studio, nastavte **identifikátor sady prostředků** k `com.MyOpenGLESApp`.

   ![Identifikátor sady prostředků Xcode](../cross-platform/media/cppmdd-opengles-iosxcodeid.png "CPPMDD_OpenGLES_iOSXcodeId")

1. Chcete-li povolit automatické podepisování, zkontrolujte. Automaticky spravovat podepisování **.

   ![Automatické podepisování Xcode](../cross-platform/media/cppmdd-opengles-iosxcodesign.png "CPPMDD_OpenGLES_iOSXcodeSign")

1. Vyberte název týmu Apple ID, které jste přidali jako vývoj **týmu**.

   ![Xcode týmu](../cross-platform/media/cppmdd-opengles-iosxcodeteam.png "CPPMDD_OpenGLES_iOSXcodeTeam")

### <a name="to-build-and-run-the-ios-app-on-an-ios-device"></a>Sestavte a spusťte aplikaci pro iOS na zařízení s iOS

1. Spuštění vzdáleného agenta na počítači Mac a ověřte, že Visual Studio je spárováno s počítačem vzdáleného agenta. Spuštění vzdáleného agenta, otevřete okno aplikaci terminál a zadejte `vcremote`. Další informace najdete v tématu [konfigurace vzdáleného agenta v sadě Visual Studio](../cross-platform/install-and-configure-tools-to-build-using-ios.md#ConfigureVS).

   ![Okno terminálu na Macu vcremote](../cross-platform/media/cppmdd_common_vcremote.png "CPPMDD_common_vcremote")

1. Připojit zařízení s Iosem do vašeho macu. Po připojení zařízení k počítači poprvé, upozornění se vás zeptá, zda důvěřujete počítače k přístupu k zařízení. Povolte zařízení důvěřovat macu.

1. V sadě Visual Studio, pokud ještě není vybraná, zvolte platformu řešení z **platformy řešení** rozevíracím seznam založený na procesoru zařízení. V tomto příkladu je **ARM64** procesoru.

   ![Nastavte platformu řešení na ARM64](../cross-platform/media/cppmdd-opengles-pickplatformarm64.png "CPPMDD_OpenGLES_SolutionPlatARM64")

1. V Průzkumníku řešení otevřete místní nabídku pro projekt MyOpenGLESApp.iOS.Application a zvolte **uvolnit projekt** uvolnit projekt.

1. Znovu, otevřete místní nabídku pro projekt uvolněn MyOpenGLESApp.iOS.Application a zvolte **upravit project.pbxproj** pro úpravu souboru projektu. V `project.pbxproj` souboru, vyhledejte `buildSettings` atribut a přidat `DEVELOPMENT_TEAM` pomocí vašeho týmu Apple ID. Následující snímek obrazovky ukazuje příklad hodnotu `123456ABC` pro tým Apple ID. Vrátí hodnotu Apple ID týmu z nástroje Xcode. Přejděte na **nastavení sestavení** a podržte ukazatel myši nad název týmu vývoje zobrazíte popis. Popisek zobrazuje ID vašeho týmu.

   ![Nastavení vývojového týmu](../cross-platform/media/cppmdd-opengles-iosdevelopmentteam.png "CPPMDD_OpenGLES_iOSDevelopmentTeam")

1. Zavřít `project.pbxproj` soubor, pak otevřete místní nabídku pro projekt uvolněn MyOpenGLESApp.iOS.Application a zvolte **znovu načíst projekt** k opětovnému načtení projektu.

1. Nyní sestavte projekt MyOpenGLESApp.iOS.Application tak, že otevřete místní nabídku pro projekt a výběrem **sestavení**.

   ![Vytvoření projektu aplikace iOS](../cross-platform/media/cppmdd_opengles_iosbuild.png "CPPMDD_OpenGLES_iOSBuild")

   V okně výstupu zobrazí výstup z procesu sestavení pro statické knihovny iOS a aplikace pro iOS. Na počítači Mac, běží vzdálený agent zobrazí v okně terminálu na příkazu a přenos souborů aktivity.

   Na počítači Mac můžete být vyzváni povolit podepisování kódu pro přístup k řetězci klíčů. Zvolte **povolit** pokračujte.

1. Zvolte zařízení s Iosem, na panelu nástrojů a spusťte tak aplikaci na vašem zařízení připojených do vašeho macu. Pokud aplikace se nespustí, ověřte, že zařízení poskytuje oprávnění pro aplikace nasazené na zařízení spouštět. Tato oprávnění můžete nastavit tak, že přejdete do **nastavení** > **Obecné** > **správy zařízení** na zařízení. Vyberte svůj účet pro vývojáře aplikací, váš účet vztahu důvěryhodnosti a ověřte, aplikace. Zkuste znovu spustit aplikaci v sadě Visual Studio.

   ![aplikace pro iOS v zařízení s Iosem](../cross-platform/media/cppmdd-opengles-iosdevice.png "CPPMDD_OpenGLES_iOSDevice")
   
   Po zahájení vaší aplikace můžete nastavit zarážky a pomocí ladicího programu sady Visual Studio zkoumat místních hodnot, Zobrazit zásobník volání a podívejte se na hodnoty.

   ![Ladicí program na zarážce v aplikaci pro iOS](../cross-platform/media/cppmdd_opengles_iosdebug.png "CPPMDD_OpenGLES_iOSDebug")

1. Stisknutím klávesy **Shift**+**F5** chcete zastavit ladění.

   Vygenerovaný iOS aplikace a knihovny projektů vložte kód jazyka C++ ve statické knihovně, která implementuje pouze sdílený kód. Většinu kódu aplikace probíhá `Application` projektu. Volání do sdílené knihovny kódu v této šabloně projektu se provádí v *GameViewController.m* souboru. Pokud chcete vytvořit aplikaci pro iOS, použije sada Visual Studio sadu nástrojů platformy Xcode, který vyžaduje komunikaci se vzdáleným klientem, který běží na macu

   Visual Studio přenese soubory projektu a odesílá příkazy ke vzdálenému klientovi k sestavení aplikace pomocí Xcode. Vzdálený klient zasílá sestavení informace o stavu zpět do sady Visual Studio. Když aplikace vytvořila úspěšně, můžete odesílat příkazy ke spuštění a ladění aplikace Visual Studio. V ladicím programu sady Visual Studio řídí aplikaci spuštěnou na zařízení s Iosem, která jsou připojená do vašeho macu. Visual Studio mapuje vlastností v projektu StaticLibrary možnosti používá ke kompilaci, propojení a ladění na cílovou platformu iOS. Podrobnosti o kompilátoru příkazového řádku, otevřete **stránky vlastností** dialogové okno pro MyOpenGLESApp.iOS.StaticLibrary projektu.

## <a name="customize-your-apps"></a>Přizpůsobení aplikací

Můžete upravit sdíleným kódem C++ pro přidání nebo změnu běžné funkce. Je nutné změnit volání do sdíleného kódu ve `MyOpenGLESApp.Android.NativeActivity` a `MyOpenGLESApp.iOS.Application` projekty tak, aby odpovídaly. Makra preprocesoru můžete určit oddíly pro konkrétní platformu v společný kód. Makro preprocesoru `__ANDROID__` je předdefinovaná při sestavení pro Android. Makro preprocesoru `__APPLE__` je předdefinovaná při sestavení pro iOS.

Zobrazit informace IntelliSense pro konkrétní projekt platformu, vyberte projekt v rozevírací nabídce přepínání kontextu na navigačním panelu v horní části okna editoru.

![Projekt přepínání kontextu rozevírací seznam v editoru](../cross-platform/media/cppmdd_opengles_contextswitcher.png)

Technologie IntelliSense problémy v kódu, který se používá v aktuálním projektu jsou označené červenou vlnovkou. Problémy v jiných projektech jsou označené fialovou vlnovkou. Visual Studio nepodporuje kód zabarvení ani IntelliSense pro soubory v jazyce Java nebo Objective-C. Můžete však stále upravovat zdrojové soubory a změnit prostředky, které chcete nastavit název vaší aplikace, ikona a další podrobnosti implementace.
