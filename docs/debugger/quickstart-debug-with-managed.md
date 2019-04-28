---
title: Ladění spravovaného kódu | Dokumentace Microsoftu
description: Ladění jazyka C# nebo Visual Basic pomocí ladicího programu sady Visual Studio
ms.custom: mvc
ms.date: 03/18/2018
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a5e39778a2d503470629f6c8b7c9243b9dc69cf3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62903799"
---
# <a name="quickstart-debug-with-c-or-visual-basic-using-the-visual-studio-debugger"></a>Rychlý start: Při ladění pomocí C# nebo Visual Basic pomocí ladicího programu sady Visual Studio

Ladicí program sady Visual Studio poskytuje mnoha výkonným funkcím, které vám pomůžou ladit vaše aplikace. Toto téma poskytuje rychlý způsob, jak Seznamte se s některými základními funkcemi.

## <a name="create-a-new-project"></a>Vytvoření nového projektu

1. Otevřít Visual Studio a vytvořte nový projekt.

    ::: moniker range=">=vs-2019"
    Stisknutím klávesy **Esc** zavřete okno start. Typ **Ctrl + Q** otevřete do vyhledávacího pole zadejte **konzoly**, zvolte **šablony**, klikněte na tlačítko **vytvořit nový projekt Konzolová aplikace (.NET Core)**. V dialogovém okně, které se zobrazí, zvolte **vytvořit**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**. V levém podokně **nový projekt** dialogovém okně **Visual C#** , zvolte **.NET Core**a potom v prostředním podokně vyberte **aplikace konzoly (.NET Core)**. Zadejte název, například **MyDbgApp** a klikněte na tlačítko **OK**.
    ::: moniker-end

     Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, přejděte na **nástroje** > **získat nástroje a funkce...** , který otevře instalačního programu sady Visual Studio. Zvolte **vývoj desktopových aplikací .NET** a **.NET Core** úloh, klikněte na tlačítko **změnit**.

    Visual Studio vytvoří projekt.

1. V *Program.cs* nebo *Module1.vb*, nahraďte následující kód

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
        }
    }
    ```

    ```vb
    Module Module1
        Sub Main()
        End Sub
    End Module
    ```

    s tímto kódem:

    ```csharp
    class Program
    {
        private static void doWork()
        {
            LinkedList<int> c1 = new LinkedList<int>();

            c1.AddLast(10);
            c1.AddLast(20);

            LinkedList<int> c2 = new LinkedList<int>(c1);
            int i = c2.First.Value;
            int j = c2.First.Value;
            Console.Write("The first element is ");
            Console.Write(i);
            Console.Write("\n");
            Console.Write("The second element is ");
            Console.Write(j);
            Console.Write("\n");

        }

        static int Main()
        {
            // using namespace std;
            doWork();
            return 0;

        }
    }
    ```

    ```vb
    Imports System.Collections.Generic

    Namespace MyDbgApp
        Class Program
            Private Shared Sub doWork()
                Dim c1 As New LinkedList(Of Integer)()

                c1.AddLast(10)
                c1.AddLast(20)

                Dim c2 As New LinkedList(Of Integer)(c1)
                Dim i As Integer = c2.First.Value
                Dim j As Integer = c2.First.Value
                Console.Write("The first element is ")
                Console.Write(i)
                Console.Write(vbLf)
                Console.Write("The second element is ")
                Console.Write(j)
                Console.Write(vbLf)

            End Sub

            Public Shared Function Main() As Integer
                ' using namespace std;
                doWork()
                Return 0

            End Function
        End Class
    End Namespace
    ```

    > [!NOTE]
    > V jazyce Visual Basic, ujistěte se, že spouštěcí objekt je nastavena na `Sub Main` (**vlastnosti > aplikace > spouštěcí objekt**).

## <a name="set-a-breakpoint"></a>Nastavení zarážky

A *zarážku* je značku, která určuje, kde by měl Visual Studio pozastavit spuštěného kódu, se můžete podívat na hodnoty proměnných nebo chování paměti nebo zda je získávání běhových větve kódu. Je nejzákladnější funkce ladění.

1. Nastavit zarážku, klikněte na ovládací prvek vlevo od `doWork` volání funkce (nebo vyberte řádek kódu a stiskněte klávesu **F9**).

    ![Nastavit zarážku](../debugger/media/dbg-qs-set-breakpoint-csharp.png "nastavte zarážku")

2. Nyní stiskněte **F5** (nebo zvolte **ladit > Spustit ladění**).

    ![Na zarážku,](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "na zarážku")

    Ladicí program pozastaví, kde nastavit zarážku. Příkaz, kde je pozastaven spuštění ladicího programu a aplikace je označen žlutou šipkou. Řádek s `doWork` ještě neprovedlo volání funkce.

    > [!TIP]
    > Pokud máte zarážku ve smyčce nebo rekurzi, nebo pokud máte mnoho zarážky, které často projdete, použijte [podmíněné zarážky](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) abyste měli jistotu, že váš kód je pozastavený, pouze v případě, že jsou splněny konkrétní podmínky. Podmíněné zarážky můžete ušetřit čas a ji můžou také usnadňují ladění problémů, které je těžké reprodukovat.

## <a name="navigate-code"></a>Vyhledání kódu

Existují různé příkazy dáte pokyn, aby ladicí program pokračovat. Ukážeme příkaz navigace užitečné kód, který je k dispozici od verze Visual Studio 2017.

Během pozastavení na zarážce, najeďte myší příkaz `c1.AddLast(20)` až do zelené **běžet do kliknutí** tlačítko ![běžet do kliknutí](../debugger/media/dbg-tour-run-to-click.png "RunToClick") se zobrazí a potom stiskněte klávesu **Běžet do kliknutí** tlačítko.

![Běžet do kliknutí](../debugger/media/dbg-qs-run-to-click-csharp.png "běžet do kliknutí")

Aplikace pokračuje v provádění, volání `doWork`a pozastaví na řádek kódu, které jste klepnuli na tlačítku.

Běžné klávesové příkazy používá k procházejte kódem po krocích zahrnují **F10** a **F11**. Další podrobné pokyny najdete v tématu [nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md).

## <a name="inspect-variables-in-a-datatip"></a>Kontrolovat proměnné v datovém tipu

1. Na aktuálním řádku kódu (označená žlutou provádění ukazatel), najeďte myší `c1` objektu pomocí myši a zobrazit datatip.

    ![Zobrazit datatip](../debugger/media/dbg-qs-data-tip-csharp.png "zobrazit datatip")

    Datatip se dozvíte, aktuální hodnota `c1` proměnné a umožňuje vám umožní zkontrolovat její vlastnosti. Při ladění, pokud se zobrazí hodnotu, kterou nečekáte, pravděpodobně chyby v předchozích nebo volání řádků kódu.

2. Rozbalení datového tipu se podívat na aktuální hodnoty vlastností `c1` objektu.

3. Pokud chcete oblast připnout datatip tak, aby se může nadále zobrazovat hodnota `c1` když je kód spuštěn, kliknutím na ikonu Připnutí malé. (Definovaného datového tipu můžete přesunout do vhodného umístění.)

## <a name="edit-code-and-continue-debugging"></a>Úprava kódu a pokračování ladění

Pokud zjistíte změnu, kterou chcete testovat ve vašem kódu, zatímco uprostřed relaci ladění, vám pomůžou, příliš.

1. Klikněte na druhou instanci `c2.First.Value` a změňte `c2.First.Value` k `c2.Last.Value`.

2. Stisknutím klávesy **F10** (nebo **ladit > Krokovat s přeskočením**) několikrát k přechodu ladicí program a spusťte upravený kód.

    ![Upravit a pokračovat](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "upravit a pokračovat")

    **F10** přejde ladicí program jeden příkaz v době, ale postup přes funkce místo krokování do nich (kód, který můžete přeskočit, stále provádí).

Další informace o používání edit-and-continue a na omezení funkcí najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak spustit ladicí program, krokovat kód a můžete kontrolovat proměnné. Můžete chtít získat podrobný přehled funkcí ladicího programu spolu s odkazy na další informace.

> [!div class="nextstepaction"]
> [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
