---
title: "Začínáme s C++ v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 99c73344-86ba-4b08-9e15-f6111cc04185
caps.latest.revision: "18"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 48f2bb4e61ca6a4f9a9464a6b67a3218b418c8ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-with-c-in-visual-studio"></a>Začínáme s C++ v sadě Visual Studio
Provedením tohoto návodu budete seznámit se s řadu nástrojů a dialogových oken, které můžete použít při vývoji aplikací pomocí sady Visual Studio. Vytvoříte jednoduchý text "Hello, World" – styl aplikace, zatímco další informace o práci v integrované vývojové prostředí (IDE).  
  
 Toto téma obsahuje následující oddíly:  
  
 [Přihlaste se k sadě Visual Studio](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_Configure)  
  
 [Vytvoření jednoduché aplikace](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_CreateApp)  
  
 [Přidejte kód do aplikace](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_AddCode)  
  
 [Ladění a testování aplikace](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_DebugTest)  
  
 [Sestavení prodejní verze aplikace](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_BuildRelease)  
  
##  <a name="BKMK_Configure"></a>Přihlaste se k sadě Visual Studio  
 Při prvním spuštění sady Visual Studio, budete mít možnost se přihlásit pomocí účtu Microsoft jako živé nebo aplikace Outlook. Přihlášení umožňuje nastavení pro synchronizaci ve všech zařízeních. Další informace najdete v tématu [přihlášení k sadě Visual Studio](../ide/signing-in-to-visual-studio.md)  
  
 Obrázek 1: Visual Studio – sada IDE  
  
 ![IDE s Visual C & č. 43; & č. 43; nastavení použitá](../ide/media/c--ide_defaultenvironmentlayout.png "IDE_DefaultEnvironmentLayout C ++")  
  
 Po otevření sady Visual Studio, zobrazí se tři základní součásti rozhraní IDE: nástroj windows, nabídek a panelů nástrojů a místo hlavní okno. Nástroje systému windows jsou ukotveno na levé a pravé straně okna aplikace s **Snadné spuštění**, panelu nabídek a standardním panelu nástrojů v horní části. Obsahuje centru okna aplikace **– úvodní stránka**. Když otevřete řešení nebo projektu, editory a návrhářů, zobrazí se v tento prostor. Při vývoji aplikace, budete tráví většinu doby v této oblasti centrální.  
  
##  <a name="BKMK_CreateApp"></a>Vytvoření jednoduché aplikace  
 Když vytvoříte aplikaci v sadě Visual Studio, nejprve vytvoříte projekt a řešení. V tomto příkladu vytvoříte konzolovou aplikaci systému Windows.  
  
#### <a name="to-create-a-console-app"></a>K vytvoření konzolové aplikace  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
     ![V řádku nabídek zvolte soubor, nový, projektu](../ide/media/exploreide-filenewproject.png "ExploreIDE FileNewProject")  
  
2.  V **Visual C++** kategorie, vyberte **Konzolová aplikace Win32** šablony a potom název projektu `GreetingsConsoleApp`.  
  
     ![Šablony aplikace Win32 konzoly](../ide/media/c--ide_newprojectdlg.png "IDE_NewProjectDlg C ++")  
     Dialogové okno vaší může mít různé možnosti, v závislosti na tom, co jste nainstalovali. Pokud nevidíte šablony projektů Visual C++, budete muset přejít zpět na instalační program a nainstalujte C++ zatížení.
  
3.  Jakmile se zobrazí v Průvodce vytvořením aplikace Win32, vyberte **Dokončit** tlačítko.  
  
     ![Průvodce vytvořením aplikace Win32 konzoly](../ide/media/c--ide_win32consoleappwizard.png "IDE_Win32ConsoleAppWizard C ++")  
  
 GreetingsConsoleApp projektu a řešení, se základní soubory pro konzoly aplikace Win32, se vytváří a automaticky načíst do **Průzkumníku řešení**. Soubor GreetingsConsoleApp.cpp je otevřen v editoru kódu. Následující položky se zobrazí v **Průzkumníku řešení**:  
  
 Obrázek 4: Položky projektu  
  
 ![Soubory v Průzkumníku řešení](../ide/media/c--ide_solutioncontents.png "IDE_SolutionContents C ++")  
  
##  <a name="BKMK_AddCode"></a>Přidejte kód do aplikace  
 Dále přidáte kód, který zobrazí slovo "Hello" v okně konzoly.  
  
#### <a name="to-display-hello-in-the-console-window"></a>Chcete-li zobrazit "text Hello" v okně konzoly  
  
1.  V souboru GreetingsConsoleApp.cpp zadejte prázdný řádek před řádek `return 0;` a potom zadejte následující kód:  
  
    ```  
    cout << "Hello\n";  
    ```  
  
     Red vlnovkou řádku se zobrazí pod `cout`. Pokud na něj přejdete, zobrazí se chybová zpráva.  
  
     ![Text Chyba cout](../ide/media/c--ide_couterror.png "IDE_CoutError C ++")  
  
     Chybová zpráva se zobrazí také v **seznam chyb** okno. Okno můžete zobrazit výběrem **zobrazení**, **seznam chyb** v řádku nabídek.  
  
     [cout](/cpp/standard-library/iostream) je součástí \<iostream > soubor hlaviček.  
  
2.  Zahrnout hlavičku iostream, zadejte následující kód po `#include "stdafx.h"`:  
  
    ```  
    #include <iostream>  
    using namespace std;  
    ```  
  
     Pravděpodobně si všimli, že se nezobrazují pole jako jste zadali kód, poskytuje doporučení pro znaky, které jste zadali. Toto pole je součástí C++ IntelliSense, která poskytuje kódování výzvy, včetně výpis členy třídy nebo rozhraní a informace o parametrech. Můžete taky fragmenty kódu, které jsou předdefinované bloky kódu. Další informace najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md) a [fragmenty kódu](../ide/code-snippets.md).  
  
     Red vlnovkou řádku pod `cout` zmizí při opravte chybu.  
  
3.  Uložte změny do souboru.  
  
     ![Kód, který opraví chyba cout](../ide/media/c--ide_coutfix.png "IDE_CoutFix C ++")  
  
##  <a name="BKMK_DebugTest"></a>Ladění a testování aplikace  
 Můžete ladit GreetingsConsoleApp zobrazíte, zda se v okně konzoly zobrazí slovo "Hello".  
  
#### <a name="to-debug-the-application"></a>K ladění aplikace  
  
-   Spuštění ladicího programu.  
  
     ![Spuštění ladění příkazu v nabídce ladění](../ide/media/exploreide-startdebugging.png "ExploreIDE StartDebugging")  
  
     Ladicí program spustí a spouští kód. V okně konzoly (samostatném okně, které vypadá příkazového řádku) se zobrazí na několik sekund, ale zavře rychle, když se zastaví ladicí program. Chcete-li zobrazit text, musíte nastavit zarážky pro zastavení spuštění programu.  
  
#### <a name="to-add-a-breakpoint"></a>Chcete-li přidat zarážky  
  
1.  Přidejte zarážku z řádku nabídek v řádku `return 0;`. Také klepnutí na levém okraji nastavit zarážky.  
  
     ![Přepnout zarážku – příkaz v nabídce ladění](../ide/media/exploreide-togglebreakpoint.png "togglebreakpoint ExploreIDE –")  
  
     Na levém okraji okna editoru se vedle řádku kódu zobrazí červený kruh.  
  
2.  Zvolte klávesy F5 spusťte ladění.  
  
     Ladicí program spustí, a zobrazí se okno konzoly s slovo **Hello**.  
  
     ![Text v okně příkazového řádku Windows Hello](../ide/media/c--ide_hellocommandwindow.png "IDE_HelloCommandWindow C ++")  
  
3.  Stiskněte SHIFT + F5 ukončete ladění.  
  
 Další informace najdete v tématu [projekty konzoly](../debugger/debugging-preparation-console-projects.md).  
  
##  <a name="BKMK_BuildRelease"></a>Sestavení prodejní verze aplikace  
 Teď, když ověříte, že vše funguje, můžete připravit sestavení pro vydání aplikace.  
  
#### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Vyčištění souborů řešení a sestavení verze pro vydání  
  
1.  V řádku nabídek odstraňte zprostředkující soubory a výstupní soubory, které byly vytvořeny během předchozí sestavení.  
  
     ![Příkaz Vyčistit řešení v nabídce sestavení](../ide/media/exploreide-cleansolution.png "ExploreIDE CleanSolution")  
  
2.  Změnit konfiguraci sestavení GreetingsConsoleApp z **ladění** k **verze**.  
  
     ![Sestavení verzi aplikace](../ide/media/c--ide_changingbuildtorelease.png "IDE_ChangingBuildtoRelease C ++")  
  
3.  Sestavte řešení.  
  
     ![Sestavit řešení – příkaz v nabídce sestavení](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")  
  
 Blahopřejeme k dokončení tohoto návodu! Pokud chcete prozkoumat další příklady, přečtěte si téma [Visual Studio – ukázky](../ide/visual-studio-samples.md).  
  
## <a name="see-also"></a>Viz také  
 [Pomocí sady Visual Studio IDE pro vývoj plochy C++](/cpp/ide/using-the-visual-studio-ide-for-cpp-desktop-development)   
 [Návod: Vytvoření jednoduché aplikace s Visual C# nebo Visual Basic](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)   
 [Tipy pro vyšší produktivitu pro sadu Visual Studio](../ide/productivity-tips-for-visual-studio.md)   
 [Visual Studio – ukázky](../ide/visual-studio-samples.md)   
 [Začít s vývojem pomocí sady Visual Studio](../ide/get-started-developing-with-visual-studio.md)