---
title: "Ladění spravovaného kódu pomocí ladicího programu sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 03/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 212da1e214e6157f3e072df6466436883eced8f6
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="debug-with-managed-code-using-the-visual-studio-debugger"></a>Ladění spravovaného kódu pomocí ladicího programu sady Visual Studio

Ladicí program Visual Studio poskytuje mnoho výkonné funkce, které vám pomůže při ladění aplikace. Toto téma poskytuje rychlý způsob, jak další některé základní funkce.

## <a name="create-a-new-project"></a>Vytvoření nového projektu 

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

2. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **.NET Core**a potom v prostředním podokně vyberte **konzolové aplikace (.NET Core)**.

     Pokud nevidíte **konzolové aplikace (.NET Core)** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **vývoj aplikací .NET** a **.NET Core** zatížení, zvolte **upravit**.

3. Zadejte název jako **MyDbgApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

4. V Program.cs nebo Module1.vb nahraďte následujícím kódem

    ```c#
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

    ```c#
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
    > V jazyce Visual Basic, ujistěte se objekt spuštění je nastavena na `Sub Main` (**vlastnosti > aplikace > spouštěcí objekt**).

## <a name="set-a-breakpoint"></a>Nastavit zarážky

A *zarážek* je značku, která určuje, kde by měl Visual Studio pozastavení vaší spuštěného kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda je získávání spustit větev kódu. Je nejzákladnější funkce při ladění.

1. Chcete-li nastavit bod přerušení, klikněte na tlačítko v mřížky nalevo od `doWork` volání funkce (nebo vyberte řádek kódu a stiskněte klávesu **F9**).

    ![Nastavit zarážky](../debugger/media/dbg-qs-set-breakpoint-csharp.png "nastavit zarážky")

2. Nyní stiskněte **F5** (nebo zvolte **ladění > Spustit ladění**).

    ![Stiskněte tlačítko zarážku](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "dosáhl zarážky")

    Ladicí program zastaví, kde nastavit bod přerušení. Příkaz, kde je pozastaven spuštění ladicího programu a aplikace je indikován žlutý šipku. Souladu se zásadami `doWork` volání funkce ještě nebyla spuštěna.

    > [!TIP]
    > Pokud máte zarážka v smyčky nebo rekurze, nebo pokud máte mnoho zarážky, které často krok prostřednictvím, použijte [podmíněného zarážek](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) a ujistěte se, že kód pozastaven jenom v případě, že jsou splněny určité podmínky. Podmíněné zarážky můžete ušetřit čas a ho můžete taky usnadňují ladění problémů, které se těžko reprodukovat.

## <a name="navigate-code"></a>Přejděte kódu

Existují jiné příkazy dáte pokyn, aby ladicí program pokračovat. Ukážeme příkaz navigační užitečné kód, který je nového ve Visual Studio 2017.

Při pozastavena u zarážky, najeďte myší na příkaz `c1.AddLast(20)` dokud zeleným **spustit a klikněte na tlačítko** tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick") se zobrazí a potom stiskněte klávesu **Spustit a klikněte na tlačítko** tlačítko.

![Spustit a klikněte na tlačítko](../debugger/media/dbg-qs-run-to-click-csharp.png "spustit a klikněte na")

Aplikace pokračuje v provádění volání `doWork`a pozastaví na řádek kódu, kde kliknutí na tlačítko.

Běžné příkazy klávesnice umožňuje zahrnout krok prostřednictvím kódu **F10** a **F11**. Další podrobné pokyny najdete v tématu [začátečníka](../debugger/getting-started-with-the-debugger.md).

## <a name="inspect-variables-in-a-datatip"></a>Zkontrolujte proměnné v datového tipu

1. V aktuálním řádku kódu (označená žlutou provádění ukazatel), najeďte myší `c1` objekt se ukazatel myši zobrazíte datového tipu.

    ![Zobrazení datového tipu](../debugger/media/dbg-qs-data-tip-csharp.png "zobrazení datového tipu")

    Popis dat se dozvíte, aktuální hodnota `c1` proměnné a umožňuje zkontrolovat její vlastnosti. Při ladění, pokud se zobrazí hodnota, kterou nepředpokládáte, pravděpodobně chyby v předchozích nebo volání řádků kódu. 

2. Rozbalte popis dat se podívat na aktuální hodnoty vlastností `c1` objektu.

3. Pokud chcete připnout popis dat tak, aby se může nadále zobrazovat hodnota `c1` při je kód spuštěn, klikněte na ikonu malý kód pin. (Popis definovaného dat můžete přesunout do vhodného umístění.)

## <a name="edit-code-and-continue-debugging"></a>Kód upravit a pokračovat, ladění

Pokud identifikovat změny, která chcete testovat ve vašem kódu při uprostřed relace ladění, můžete to udělat, příliš.

1. Klikněte na druhou instanci `c2.First.Value` a změňte `c2.First.Value` k `c2.Last.Value`.

2. Stiskněte klávesu **F10** (nebo **ladění > Krokovat s přeskočením**) několikrát k posunutí ladicího programu a spusťte upravená kód.

    ![Upravit a pokračovat](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "upravit a pokračovat")

    **F10** přejde ladicí program jeden příkaz na dobu, ale kroky prostřednictvím funkce místo zanoříte se do nich (kód, který můžete přeskočit stále provádí).

Další informace o používání upravit a pokračovat a na omezení funkcí najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Další kroky

V tomto kurzu když jste se naučili postup spuštění ladicího programu, krok prostřednictvím kódu a zkontrolovat proměnné. Chcete získat přehled funkcí ladicího programu spolu s odkazy na další informace.

> [!div class="nextstepaction"]
> [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
