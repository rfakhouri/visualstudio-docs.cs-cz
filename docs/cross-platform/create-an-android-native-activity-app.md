---
title: "Vytvoření aplikace pro Android nativní aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 884014b1-5208-45ec-b0da-ad0070d2c24d
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bf42c5b05ec68546bee938746f3e3b774303e5fb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="create-an-android-native-activity-app"></a>Vytvoření aplikace pro Android nativní aktivity
Když instalujete Visual C++ pro vývoj mobilních řešení pro různé platformy možnost, Visual Studio 2015 lze vytvářet plně funkční aplikace pro Android nativní aktivity. Android Kit pro nativní vývoj (NDK) je sada nástrojů, který umožňuje implementovat většina aplikací systému Android pomocí čistém kódu C/C++. Nějaký kód Java JNI funguje jako spojovací umožňující kódu C/C++ pro interakci s Android. Android NDK zavedla možnost vytvářet nativní aktivity aplikací s Androidem 9 úroveň rozhraní API. Nativní kód aktivity se používá pro vytváření hraní a grafické náročné aplikace, které používají Unreal Engine nebo OpenGL. Toto téma vás provede vytvoření jednoduché aplikace nativní aktivity, která používá OpenGL. Další témata provede vývojáře životní cyklus úpravy, vytváření, ladění a nasazování kód nativní aktivity.  
  
 [Požadavky](#req)   
 [Vytvoření nového projektu nativní aktivity](#Create)   
 [Sestavení a spuštění aplikace Android nativní aktivity výchozí](#BuildHello)  
  
##  <a name="req"></a>Požadavky  
 Před vytvořením aplikace Android nativní aktivity, musí se ujistěte, jste splněny všechny požadavky na systém a nainstalovat možnost Visual C++ vývoj mobilních řešení ve Visual Studiu 2015. Další informace najdete v tématu [nainstalovat Visual C++ pro vývoj mobilních řešení pro různé platformy](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Ujistěte se, že požadované nástroje třetích stran a sady SDK jsou součástí instalace, a je nainstalovaný Microsoft Visual Studio Emulator for Android.  
  
##  <a name="Create"></a>Vytvoření nového projektu nativní aktivity  
 V tomto kurzu budete nejprve vytvořte nový projekt Android nativní aktivitu a potom sestavte a spusťte výchozí aplikace v emulátor sady Visual Studio pro Android.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Otevřete Visual Studio. Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V **nový projekt** dialogovém **šablony**, zvolte **Visual C++**, **křížové platformy**a potom vyberte  **Aktivita nativní aplikace (Android)** šablony.  
  
3.  Zadejte název jako aplikace `MyAndroidApp`a potom zvolte **OK**.  
  
     ![Vytvoření projektu nativní aktivity](../cross-platform/media/cppmdd_newproject.PNG "CppMDD_NewProject")  
  
     Visual Studio vytvoří nové řešení a otevře Průzkumníka řešení.  
  
     ![Nativní aktivity projekt v Průzkumníkovi řešení](../cross-platform/media/cppmdd_rc_na_solutionexp.PNG "CPPMDD_RC_NA_SolutionExp")  
  
 Nové řešení aplikace Android nativní aktivity obsahuje dva projekty:  
  
-   **MyAndroidApp.NativeActivity** obsahuje odkazy a spojovací kód pro aplikaci, kterou chcete spustit jako nativní aktivity v systému Android. Implementace vstupních bodů z kódu spojovací jsou main.cpp. Předkompilované hlavičky jsou pch.h. Tento projekt aplikace nativní aktivity zkompilován soubor .so sdílené knihovny, který je převzata balení projektu.  
  
-   **MyAndroidApp.Packaging** vytvoří soubor .apk pro nasazení na emulátoru nebo zařízení s Androidem. Tato položka obsahuje prostředků a kde nastavíte vlastnosti manifestu souboru AndroidManifest.xml. Obsahuje taky build.xml soubor, který řídí procesu sestavení Ant. Ho jako projekt po spuštění ve výchozím nastavení, takže ho můžete nasadit a spustit přímo ze sady Visual Studio.  
  
##  <a name="BuildHello"></a>Sestavení a spuštění aplikace Android nativní aktivity výchozí  
 Sestavení a spuštění aplikace generované šablonu, kterou chcete ověřit instalaci a nastavení. Pro tento test počáteční spuštění aplikace na jeden z profilů zařízení nainstalovat pomocí emulátor sady Visual Studio pro Android. Pokud dáváte přednost k testování aplikace na jiný cíl, můžete načíst cílový emulátoru nebo připojení zařízení k počítači.  
  
#### <a name="to-build-and-run-the-default-native-activity-app"></a>Sestavení a spuštění výchozí aktivity nativní aplikace  
  
1.  Pokud již není vybrána, vyberte **x86** z **platformy řešení** rozevíracího seznamu.  
  
     ![Výběr řešení platformy rozevírací x86](../cross-platform/media/cppmdd_rc_na_solution_x86.png "CPPMDD_RC_NA_Solution_x86")  
  
     Pokud **platformy řešení** není zobrazen seznam, vyberte **platformy řešení** z **tlačítka Přidat nebo odebrat** seznamu a potom vyberte vaši platformu.  
  
2.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
     Ve výstupním okně zobrazí výstup procesu sestavení pro dva projekty v řešení.  
  
3.  Vyberte jednu z emulátoru VS telefon se systémem Android (x86) profily jako cíl vaše nasazení.  
  
     Pokud jste nainstalovali další emulátorů nebo připojené zařízení s Androidem, můžete je v rozevíracím seznamu cíl nasazení.  
  
4.  Stisknutím klávesy F5 spusťte ladění nebo Shift + F5 a spusťte bez ladění.  
  
     Zde je jak výchozí aplikace vypadá v emulátor sady Visual Studio pro Android.  
  
     ![Emulátor používající vaši aplikaci](../cross-platform/media/cppmdd_emulator_running_app.PNG "CppMDD_Emulator_Running_App")  
  
     Visual Studio spustí se emulátor, který přebírá několik sekund, spouštění a nasadíte tak svůj kód. Po zahájení aplikace, můžete nastavit zarážky a používat ladicí program ke kroku prostřednictvím kódu, zkontrolujte místní hodnoty a podívejte se na hodnoty.  
  
5.  Stiskněte Shift + F5 ukončete ladění.  
  
     Emulátor je samostatný proces, který stále běží. Můžete upravit, kompilace a nasazení kódu do stejné emulátoru vícekrát.