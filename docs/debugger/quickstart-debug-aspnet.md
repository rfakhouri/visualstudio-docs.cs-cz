---
title: Ladění technologie ASP.NET
description: Ladění technologii ASP.NET pomocí ladicího programu sady Visual Studio
ms.custom: mvc
ms.date: 03/16/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 5f731e5d40205776682e706aa4e32d988a76f0f0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-debug-aspnet-with-the-visual-studio-debugger"></a>Rychlý úvod: Ladění ASP.NET pomocí ladicího programu sady Visual Studio

Ladicí program Visual Studio poskytuje mnoho výkonné funkce, které vám pomůže při ladění aplikace. Toto téma poskytuje rychlý způsob, jak další některé základní funkce.

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#**, zvolte **webové**a potom v prostředním podokně vyberte **webové aplikace ASP.NET Core**.

1. Zadejte název jako **MyDbgApp** a klikněte na tlačítko **OK**.

1. V zobrazeném dialogu vyberte **webové aplikace** v prostředním podokně a pak klikněte na tlačítko **OK**.

     Pokud nevidíte **webové aplikace** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **ASP.NET** a **.NET Core** zatížení, zvolte **upravit**.

    ![Vyberte webovou aplikaci](../debugger/media/dbg-qs-aspnet-choose-web-app.png)

    Visual Studio vytvoří projekt.

1. V Průzkumníku řešení otevřete About.cshtml.cs (v rámci Pages/About.cshtml) a nahraďte následujícím kódem

    ```c#
    public void OnGet()
    {
        Message = "Your application description page.";
    }
    ```

    s tímto kódem:

    ```c#
    public void OnGet()
    {
        LinkedList<int> result = doWork();
        Message = "Result of work: " + result.First.Value + ", " + result.First.Value;
    }

    private static LinkedList<int> doWork()
    {
        LinkedList<int> c1 = new LinkedList<int>();

        c1.AddLast(10);
        c1.AddLast(20);

        LinkedList<int> c2 = new LinkedList<int>(c1);

        return c2;

    }
    ```

## <a name="set-a-breakpoint"></a>Nastavit zarážky

A *zarážek* je značku, která určuje, kde by měl Visual Studio pozastavení vaší spuštěného kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda je získávání spustit větev kódu. Je nejzákladnější funkce při ladění.

1. Chcete-li nastavit bod přerušení, klikněte na tlačítko v mřížky nalevo od `doWork` – funkce (nebo vyberte řádek kódu a stiskněte klávesu **F9**).

    ![Nastavit zarážky](../debugger/media/dbg-qs-set-breakpoint-aspnet.png)

    Je nastavena zarážka nalevo od levá složená závorka (`{`).

1. Nyní stiskněte **F5** (nebo zvolte **ladění > Spustit ladění**).

1. Po načtení webové stránky, klikněte na tlačítko **o** odkaz v horní části webové stránky.

    Ladicí program zastaví, kde nastavit bod přerušení. Příkaz, kde je pozastaven spuštění ladicího programu a aplikace je indikován žlutý šipku. Řádek s levá složená závorka (`{`) po `doWork` deklarace funkce ještě nebyla spuštěna.

    ![Stiskněte tlačítko zarážky](../debugger/media/dbg-qs-hit-breakpoint-aspnet.png)

    > [!TIP]
    > Pokud máte zarážka v smyčky nebo rekurze, nebo pokud máte mnoho zarážky, které často krok prostřednictvím, použijte [podmíněného zarážek](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) a ujistěte se, že kód pozastaven jenom v případě, že jsou splněny určité podmínky. To šetří čas a můžete také usnadňují ladění problémů, které se těžko reprodukovat.

## <a name="navigate-code"></a>Přejděte kódu

Existují jiné příkazy dáte pokyn, aby ladicí program pokračovat. Ukážeme příkaz navigační užitečné kód, který je nového ve Visual Studio 2017.

Při pozastavena u zarážky, najeďte myší na příkaz `return c2` dokud zeleným **spustit a klikněte na tlačítko** tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png) se zobrazí a potom stiskněte klávesu **spustit a klikněte na tlačítko** tlačítko.

![Spustit a klikněte na](../debugger/media/dbg-qs-run-to-click-aspnet.png)

Aplikace pokračuje v provádění a pozastaví na řádek kódu, kde kliknutí na tlačítko.

Běžné příkazy klávesnice umožňuje zahrnout krok prostřednictvím kódu **F10** a **F11**. Další podrobné pokyny najdete v tématu [začátečníka](../debugger/getting-started-with-the-debugger.md).

## <a name="inspect-variables-in-a-datatip"></a>Zkontrolujte proměnné v datového tipu

1. V aktuálním řádku kódu (označená žlutou provádění ukazatel), najeďte myší `c2` objekt se ukazatel myši zobrazíte datového tipu.

    ![Zobrazení datového tipu](../debugger/media/dbg-qs-data-tip-aspnet.png)

    Popis dat se dozvíte, aktuální hodnota `c2` proměnné a umožňuje zkontrolovat její vlastnosti. Při ladění, pokud se zobrazí hodnota, kterou nepředpokládáte, pravděpodobně chyby v předchozích nebo volání řádků kódu. 

2. Rozbalte popis dat se podívat na aktuální hodnoty vlastností `c2` objektu.

3. Pokud chcete připnout popis dat tak, aby se může nadále zobrazovat hodnota `c2` při je kód spuštěn, klikněte na ikonu malý kód pin. (Popis definovaného dat můžete přesunout do vhodného umístění.)

## <a name="edit-code-and-continue-debugging"></a>Kód upravit a pokračovat, ladění

Pokud identifikovat změny, která chcete testovat ve vašem kódu při uprostřed relace ladění, můžete to udělat, příliš.

1. V `OnGet` metoda, klikněte na druhou instanci `result.First.Value` a změňte `result.First.Value` k `result.Last.Value`.

1. Stiskněte klávesu **F10** (nebo **ladění > Krokovat s přeskočením**) několikrát k posunutí ladicího programu a spusťte upravená kód.

    ![Upravit a pokračovat](../debugger/media/dbg-qs-edit-and-continue-aspnet.png "upravit a pokračovat")

    **F10** přejde ladicí program jeden příkaz na dobu, ale kroky prostřednictvím funkce místo zanoříte se do nich (kód, který můžete přeskočit stále provádí).

Další informace o používání upravit a pokračovat a na omezení funkcí najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Další kroky

V tomto kurzu když jste se naučili postup spuštění ladicího programu, krok prostřednictvím kódu a zkontrolovat proměnné. Chcete získat přehled funkcí ladicího programu spolu s odkazy na další informace.

> [!div class="nextstepaction"]
> [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
