---
title: Ladění jazyka C++
description: Ladění nativního kódu pomocí ladicího programu sady Visual Studio
ms.custom: mvc
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: 639e430b-6d2d-46bd-b738-8c60dfb384f1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 1027e5f737bf3fc75b33c47578ae0cc107a1fb7d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-debug-with-c-using-the-visual-studio-debugger"></a>Rychlý úvod: Ladění s jazykem C++ pomocí ladicího programu sady Visual Studio

Ladicí program Visual Studio poskytuje mnoho výkonné funkce, které vám pomůže při ladění aplikace. Toto téma poskytuje rychlý způsob, jak další některé základní funkce.

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

2. V části **Visual C++**, zvolte **Windows Desktop**a potom v prostředním podokně vyberte **konzolové aplikace pro Windows**.

    Pokud nevidíte **konzolové aplikace pro Windows** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **vývoj aplikací s jazykem C++** zatížení, zvolte **upravit**.

3. Zadejte název jako **MyDbgApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

4. V MyDbgApp.cpp nahraďte následujícím kódem

    ```c++
    int main()
    {
        return 0;
    }
    ```

    s tímto kódem (neodebírejte `#include "stdafx.h"`):

    ```c++
    #include <list>  
    #include <iostream>

    using namespace std;

    void doWork()
    {
        list <int> c1;

        c1.push_back(10);
        c1.push_back(20);

        const list <int> c2 = c1;
        const int &i = c2.front();
        const int &j = c2.front();
        cout << "The first element is " << i << endl;
        cout << "The second element is " << j << endl;

    }

    int main()
    {
        doWork();
    }
    ```

## <a name="set-a-breakpoint"></a>Nastavit zarážky

A *zarážek* je značku, která určuje, kde by měl Visual Studio pozastavení vaší spuštěného kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda je získávání spustit větev kódu. Je nejzákladnější funkce při ladění.

1. Chcete-li nastavit bod přerušení, klikněte na tlačítko v mřížky nalevo od `doWork` volání funkce (nebo vyberte řádek kódu a stiskněte klávesu **F9**).

    ![Nastavit zarážky](../debugger/media/dbg-qs-set-breakpoint.png "nastavit zarážky")

2. Nyní stiskněte **F5** (nebo zvolte **ladění > Spustit ladění**).

    ![Stiskněte tlačítko zarážku](../debugger/media/dbg-qs-hit-breakpoint.png "dosáhl zarážky")

    Ladicí program zastaví, kde nastavit bod přerušení. Příkaz, kde je pozastaven spuštění ladicího programu a aplikace je indikován žlutý šipku. Souladu se zásadami `doWork` volání funkce ještě nebyla spuštěna.

    > [!TIP]
    > Pokud máte zarážka v smyčky nebo rekurze, nebo pokud máte mnoho zarážky, které často krok prostřednictvím, použijte [podmíněného zarážek](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) a ujistěte se, že kód pozastaven jenom v případě, že jsou splněny určité podmínky. Podmíněné zarážky šetří čas a můžete také usnadňují ladění problémů, které se těžko reprodukovat.

    Při pokusu o ladění chyby související s pamětí v jazyce C++, můžete taky zarážky kontrola hodnoty adres (podívejte se na hodnotu NULL) a odkazovat na počty. 

## <a name="navigate-code"></a>Přejděte kódu

Existují jiné příkazy dáte pokyn, aby ladicí program pokračovat. Ukážeme příkaz navigační užitečné kód, který je nového ve Visual Studio 2017.

Při pozastavena u zarážky, najeďte myší na příkaz `c1.push_back(20)` dokud zeleným **spustit a klikněte na tlačítko** tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick") se zobrazí a potom stiskněte klávesu **Spustit a klikněte na tlačítko** tlačítko.

![Spustit a klikněte na tlačítko](../debugger/media/dbg-qs-run-to-click.png "spustit a klikněte na")

Aplikace pokračuje v provádění volání `doWork`a pozastaví na řádek kódu, kde kliknutí na tlačítko.

Běžné příkazy klávesnice umožňuje zahrnout krok prostřednictvím kódu **F10** a **F11**. Další podrobné pokyny najdete v tématu [začátečníka](../debugger/getting-started-with-the-debugger.md).

## <a name="inspect-variables-in-a-datatip"></a>Zkontrolujte proměnné v datového tipu

1. V aktuálním řádku kódu (označená žlutou provádění ukazatel), najeďte myší `c1` objekt se ukazatel myši zobrazíte datového tipu.

    ![Zobrazení datového tipu](../debugger/media/dbg-qs-data-tip.png "zobrazení datového tipu")

    Popis dat se dozvíte, aktuální hodnota `c1` proměnné a umožňuje zkontrolovat její vlastnosti. Při ladění, pokud se zobrazí hodnota, kterou nepředpokládáte, pravděpodobně chyby v předchozích nebo volání řádků kódu. 

2. Rozbalte popis dat se podívat na aktuální hodnoty vlastností `c1` objektu.

3. Pokud chcete připnout popis dat tak, aby se může nadále zobrazovat hodnota `c1` při je kód spuštěn, klikněte na ikonu malý kód pin. (Popis definovaného dat můžete přesunout do vhodného umístění.)

## <a name="edit-code-and-continue-debugging"></a>Kód upravit a pokračovat, ladění

Pokud identifikovat změny, která chcete testovat ve vašem kódu při uprostřed relace ladění, můžete to udělat, příliš.

1. Klikněte na druhou instanci `c2.front()` a změňte `c2.front()` k `c2.back()`.

2. Stiskněte klávesu **F10** (nebo **ladění > Krokovat s přeskočením**) několikrát k posunutí ladicího programu a spusťte upravená kód.

    ![Upravit a pokračovat](../debugger/media/dbg-qs-edit-and-continue.gif "upravit a pokračovat")

    **F10** přejde ladicí program jeden příkaz na dobu, ale kroky prostřednictvím funkce místo zanoříte se do nich (kód, který můžete přeskočit stále provádí).

Další informace o používání upravit a pokračovat a na omezení funkcí najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Další kroky

V tomto kurzu když jste se naučili postup spuštění ladicího programu, krok prostřednictvím kódu a zkontrolovat proměnné. Chcete získat přehled funkcí ladicího programu spolu s odkazy na další informace.

> [!div class="nextstepaction"]
> [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
