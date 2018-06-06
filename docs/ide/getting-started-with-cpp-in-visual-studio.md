---
title: Začínáme s C++ v sadě Visual Studio
description: ''
ms.custom: mvc
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
author: corob-msft
ms.author: tglee
manager: douge
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: b49f83813bc5acd64de74a27a025bc78503902c5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747349"
---
# <a name="get-started-with-c-in-visual-studio"></a>Začínáme s C++ v sadě Visual Studio

Dokončete tento rychlý start, abyste se seznámili s řadu nástrojů a dialogových oken, které můžete použít při vývoji aplikací v jazyce C++ pomocí sady Visual Studio. Vytvoření "Hello, World" – styl konzolovou aplikaci, zatímco další informace o práci v integrované vývojové prostředí (IDE).

## <a name="prerequisites"></a>Požadavky

Nemusíte se seznamte s C++ dokončete tento rychlý start, ale měli byste se seznámit s některé obecné programování a ladění koncepty. Programování v jazyce C++ nepodporuje naučit dokumentaci sady Visual Studio. Je dobré Průvodce C++ studijních materiálů [Začínáme](https://isocpp.org/get-started) na webu ISO C++.

Pokud chcete sledovat, musíte kopie Visual Studio 2017 verze 15.3 nebo novější s **vývoj aplikací s jazykem C++** zatížení nainstalována. Rychlé informace k instalaci najdete v tématu [podpory nainstalovat C++ v sadě Visual Studio](/cpp/build/vscpp-step-0-installation).

## <a name="create-a-console-app"></a>Vytvořte aplikaci konzoly

Pokud ještě není spuštěná, spusťte Visual Studio.

![IDE s Visual C&#43; &#43; nastavení](../ide/media/get-started-cpp-ide-layout.png)

Po otevření sady Visual Studio, zobrazí se tři základní součásti rozhraní IDE: nástroj windows, nabídek a panelů nástrojů a místo hlavní okno. Nástroje systému windows jsou ukotveno na levé a pravé straně okna aplikace. **Snadné spuštění** pole řádku nabídek a standardním panelu nástrojů se nacházejí v horní části. Obsahuje centru okna **– úvodní stránka**. Když otevřete řešení nebo projektu, editory a návrhářů, zobrazí se v tento prostor. Při vývoji aplikace je většinu času stráví v této oblasti centrální.

Visual Studio použije *projekty* k uspořádání kódu pro aplikace, a *řešení* k uspořádání vašich projektů. Projekt obsahuje možnosti, konfigurace a pravidel použitý k sestavení aplikace. Spravuje taky vztah mezi soubory všechny projektu a externí soubory. Pokud chcete vytvořit aplikaci, nejprve vytvoříte nový projekt a řešení.

### <a name="to-create-a-console-app-project"></a>Vytvoření projektu aplikace konzoly

1. Na řádku nabídek zvolte **soubor > Nový > projekt** otevřete **nový projekt** dialogové okno.

   ![V řádku nabídek zvolte Soubor > Nový > Projekt](../ide/media/get-started-cpp-file-new-project-menu.png)

1. V **nový projekt** dialogovém okně, vyberte **nainstalovaná > Visual C++** Pokud ještě není zaškrtnuto. V prostředním podokně, vyberte **konzolové aplikace pro Windows** šablony. V **název** textové pole, zadejte *HelloApp*.

   ![Použití dialogového okna Nový projekt pro vytvoření projektu aplikace](../ide/media/get-started-cpp-new-project-dialog.png)

   Dialogové okno vaší může mít různé možnosti, v závislosti na sadě Visual Studio úlohy a součástí, které jste nainstalovali. Pokud nevidíte šablony projektů Visual C++, budete muset znovu spustit instalační program sady Visual Studio a nainstalovat **vývoj aplikací s jazykem C++** zatížení. Můžete to provést přímo z **nový projekt** dialogové okno. Chcete-li spustit instalační program, zvolte **otevřete instalační program Visual Studio** odkaz v dialogovém okně.

1. Vyberte **OK** tlačítko vytvořte projekt aplikace a řešení.

   HelloApp projektu a řešení, se základní soubory pro konzolovou aplikaci systému Windows, se vytváří a automaticky načíst do **Průzkumníku řešení**. *HelloApp.cpp* otevření souboru v editoru kódu. Tyto položky se zobrazí v **Průzkumníku řešení**:

   ![Soubory v Průzkumníku řešení](../ide/media/get-started-cpp-solution-explorer.png)

## <a name="add-code-to-the-app"></a>Přidejte kód do aplikace

Dál přidejte kód, který zobrazí slovo "Hello" v okně konzoly.

### <a name="to-edit-code-in-the-editor"></a>Chcete-li upravit kód v editoru

1. V *HelloApp.cpp* souboru, zadejte prázdný řádek před řádek `return 0;` a pak zadejte tento kód:

   ```cpp
   cout << "Hello\n";
   ```

   Red vlnovkou řádku se zobrazí pod `cout`. Pokud při umístění ukazatele nad ním, zobrazí se chybová zpráva.

   ![Text Chyba cout](../ide/media/get-started-cpp-intellisense-error.png)

   Chybová zpráva se zobrazí také v **seznam chyb** okno. V tomto okně můžete zobrazit výběrem **zobrazení > Seznam chyb** v řádku nabídek.

   ![Došlo k chybě v okně Seznam chyb](../ide/media/get-started-cpp-error-list.png)

   Váš kód chybí deklarace pro [std::cout](/cpp/standard-library/iostream), který se nachází v  *\<iostream >* soubor hlaviček.

1. Zahrnout *iostream* záhlaví, zadejte tento kód po `#include "stdafx.h"`:

   ```cpp
   #include <iostream>
   using namespace std;
   ```

   Pravděpodobně si všimli, že se nezobrazují pole jako jste zadali kód. Toto pole obsahuje návrhy automatické dokončování znaků, které zadáte. To je součástí C++ IntelliSense, která poskytuje kódování výzvy, včetně členů třídy nebo rozhraní a informace o parametrech. Můžete taky fragmenty kódu, které jsou předdefinované bloky kódu. Další informace najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md) a [výstřižky kódu](../ide/code-snippets.md).

   ![Opravené kódu v editoru](../ide/media/get-started-cpp-cout-fix.png)

   Red vlnovkou řádku pod `cout` zmizí při opravte chybu.

1. Chcete-li uložit změny do souboru, stiskněte **Ctrl + S**.

## <a name="build-the-app"></a>Sestavení aplikace

Je snadné sestavení vašeho kódu. Na řádku nabídek zvolte **sestavení > Sestavit řešení**. Visual Studio vytvoří řešení HelloApp a sestavy průběhu v **výstup** okno.

   ![Sestavte řešení HelloApp](../ide/media/get-started-cpp-build-solution.gif)

## <a name="debug-and-test-the-app"></a>Ladění a testování aplikace

Můžete ladit HelloApp zobrazíte, zda se v okně konzoly zobrazí slovo "Hello".

### <a name="to-debug-the-app"></a>K ladění aplikace

Chcete-li spuštění ladicího programu, zvolte **ladění > Spustit ladění** v řádku nabídek.

![Spuštění ladění příkazu v nabídce ladění](../ide/media/get-started-cpp-start-debugging-menu.png)

Ladicí program spustí a spouští kód. V okně konzoly (samostatném okně, které vypadá příkazového řádku) se zobrazí na několik sekund, ale zavře rychle, když se zastaví ladicí program. Chcete-li zobrazit text, musíte nastavit zarážky pro zastavení spuštění programu.

### <a name="to-add-a-breakpoint"></a>Chcete-li přidat zarážky

1. V editoru, umístěte kurzor na řádku `return 0;`. Na řádku nabídek zvolte **ladění > Přepnout zarážku**. Můžete také kliknutím na levém okraji nastavit zarážky.

     ![Přepnout zarážku – příkaz v nabídce ladění](../ide/media/get-started-cpp-toggle-breakpoint-menu.png)

     Na levém okraji okna editoru se vedle řádku kódu zobrazí červený kruh.

     ![Uvedené v okně okraj zarážek](../ide/media/get-started-cpp-breakpoint-set.png)

1. Chcete-li začít, ladění, stiskněte **F5**.

   Ladicí program spustí, a zobrazí se okno konzoly s slovo **Hello**.

   ![V okně konzoly text Hello](../ide/media/get-started-cpp-helloapp-window.png)

1. Chcete-li zastavit, ladění, stiskněte **Shift + F5**.

Další informace o ladění projektu v konzole najdete v tématu [konzole projekty](../debugger/debugging-preparation-console-projects.md).

## <a name="build-a-release-version-of-the-app"></a>Sestavení prodejní verze aplikace

Teď, když ověříte, že vše funguje, můžete připravit sestavení pro vydání aplikace. Verze sestavení ponechejte informace o ladění a možnosti optimalizace kompilátoru použijte k vytvoření menších, rychlejší kódu.

### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Vyčištění souborů řešení a sestavení verze pro vydání

1. Na řádku nabídek zvolte **sestavení > Vyčistit řešení** odstranit zprostředkující soubory a výstupní soubory, které byly vytvořeny během předchozí sestavení.

   ![Příkaz Vyčistit řešení v nabídce sestavení](../ide/media/get-started-cpp-clean-solution-menu.png)

1. Chcete-li změnit konfiguraci řešení pro HelloApp z **ladění** k **verze**, na panelu nástrojů vyberte ovládacího prvku konfigurace řešení v rozevírací nabídce a potom zvolte **verze**.

   ![Sestavení verze pro vydání aplikace](../ide/media/get-started-cpp-set-release-configuration.png)

1. Sestavte řešení. Na řádku nabídek zvolte **sestavení > Sestavit řešení**.

Po dokončení tohoto buildu jste vytvořili aplikaci, která můžete zkopírovat a spustit v libovolném okně příkazového řádku. Hodně postup, ale je bránu a větší věcí.

Blahopřejeme k dokončení tento rychlý start! Pokud chcete prozkoumat další příklady, přečtěte si téma [Visual Studio – ukázky](../ide/visual-studio-samples.md).

## <a name="see-also"></a>Viz také:

- [Pomocí prostředí Visual Studio IDE pro vývoj aplikací C++](/cpp/ide/using-the-visual-studio-ide-for-cpp-desktop-development)
- [Návod: Vytvoření jednoduché aplikace s C# nebo Visual Basic](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)
- [Tipy pro vyšší produktivitu pro sadu Visual Studio](../ide/productivity-tips-for-visual-studio.md)
