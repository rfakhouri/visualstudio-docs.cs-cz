---
title: 'Kurz: Vytvořit jednoduchou C# Konzolová aplikace'
description: Zjistěte, jak vytvořit konzolovou aplikaci C# v sadě Visual Studio, krok za krokem.
ms.custom: seodec18, get-started
ms.date: 03/12/2019
ms.technology: vs-ide-general
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c73212ad53389b71ee2eb2a2660cd3dcbccaad8b
ms.sourcegitcommit: 2dc924c96a6d48803c8eedc3d6781202629b41fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/11/2019
ms.locfileid: "57736910"
---
# <a name="tutorial-create-a-simple-c-console-app-in-visual-studio"></a>Kurz: Vytvořit jednoduchou C# konzolovou aplikaci v sadě Visual Studio

V tomto kurzu pro C#, Visual Studio budete používat k vytváření a spustíte aplikaci konzoly a prozkoumat některé funkce integrovaného vývojového prostředí (IDE) sady Visual Studio, když uděláte.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Pokud chcete začít, vytvoříme C# projekt aplikace. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.
   (Nebo stisknout **Ctrl**+**Shift**+**N**).

3. V levém podokně **nový projekt** dialogového okna rozbalte **C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Potom zadejte název souboru ***Kalkulačka***.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workload-optional"></a>Přidat úlohu (volitelné)

Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro různé platformy .NET Core** pracovního vytížení. Tady je způsob.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Option 1: Pomocí dialogového okna Nový projekt

1. Zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Zvolte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Option 2: Pomocí nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogového okna a v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

## <a name="create-the-app"></a>Vytvoření aplikace

Nejprve se podíváme procvičili matematiku základními celočíselnými v C#. Potom přidáme kód pro vytvoření základní kalkulačky. Další. Potom jsme budeme ladit aplikaci vyhledat a opravit chyby. A nakonec jsme upřesníte kód, který efektivnější.

### <a name="explore-integer-math"></a>Prozkoumejte matematikou celých čísel

Začněme procvičili matematiku základními celočíselnými v C#.

1. V editoru kódu odstraňte výchozí kód "Hello World".

    ![Odstranit výchozí kódu Hello World z nové kalkulačky aplikace](./media/csharp-console-calculator-deletehelloworld.png)

   Konkrétně odstranit řádek, který říká, `Console.WriteLine("Hello World!");`.

1. Místo toho zadejte Tenhle kód:

    ```csharp
            int a = 42;
            int b = 119;
            int c = a + b;
            Console.WriteLine(c);
            Console.ReadKey();
    ```

    Všimněte si, že pokud tak učiníte, funkcí IntelliSense v sadě Visual Studio nabízí možnost pro automatické dokončování položka.

    ![Animace dvojice v celé číslo matematické kód, který ukazuje funkci automatického dokončování IntelliSense v integrovaném vývojovém prostředí sady Visual Studio](./media/integer-math-intellisense.gif)

1. Zvolte **Kalkulačka** ke spuštění programu, nebo stiskněte klávesu **F5**.

   ![Klikněte na tlačítko kalkulačky ke spuštění aplikace z panelu nástrojů](./media/csharp-console-calculator-button.png)

   Otevře se okno konzoly, které zjistí součet 42 + 119, což je **161**.

    ![Okna konzoly zobrazuje výsledky matematikou celých čísel](./media/csharp-console-integer-math.png)

1. **(Volitelné)**  Změníte operátor Chcete-li změnit výsledek. Například můžete změnit `+` operátor `int c = a + b;` řádku kódu `-` pro odčítání, `*` pro násobení, nebo `/` pro dělení. Poté při spuštění programu, výsledek změny příliš.

1. Zavřete okno konzoly.

### <a name="add-code-to-create-a-calculator"></a>Přidejte kód k vytvoření Kalkulačka

Můžeme pokračovat přidáním složitější sadu Kalkulačka kódu do projektu.

1. Odstraňte veškerý kód, který se zobrazí v editoru kódu.

1. Zadejte nebo vložte následující nový kód do editoru kódu:

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then initialize to zero
                int num1 = 0; int num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```

1. Zvolte **Kalkulačka** ke spuštění programu, nebo stiskněte klávesu **F5**.

   ![Klikněte na tlačítko kalkulačky ke spuštění aplikace z panelu nástrojů](./media/csharp-console-calculator-button.png)

   Otevře se okno konzoly.

1. Zobrazení vaší aplikace v okně konzoly a postupujte podle pokynů pro přidání čísel **42** a **119**.

   Vaše aplikace by měla vypadat podobně jako na následujícím snímku obrazovky:

    ![Konzoly okno aplikace kalkulačky a zahrnuje dotazování na akce, které se má provést](./media/csharp-console-calculator.png)

### <a name="add-functionality-to-the-calculator"></a>Přidání funkce do kalkulačky

Pojďme upravit kód pro přidání dalších funkcí.

### <a name="add-decimals"></a>Přidat desetinná místa

Kalkulačka aplikace nyní přijímá a vrací celá čísla. Ale bude přesnější, můžeme přidat kód, který umožňuje desetinná čísla.

Jako na následujícím snímku obrazovky Pokud spustíte aplikaci a rozdělit číslo 42 číslem 119, sady výsledků je 0 (nula), který není přesné.

![Okno konzoly zobrazující aplikaci kalkulačky, který nevrací desítkové číslice v důsledku](./media/csharp-console-calculator-nodecimal.png)

Opravíme kód tak, aby zpracovává desetinná čísla.

1. Stisknutím klávesy **Ctrl** + **F** otevřít **najít a nahradit** ovládacího prvku.

1. Změňte každou instanci `int` proměnnou `float`.

   Ujistěte se, že přepnete **rozlišovat velikost písmen** (**Alt**+**C**) a **celá slova** (**Alt** + **W**) v **najít a nahradit** ovládacího prvku.

    ![Animace ovládacího prvku najít a nahradit ukazující, jak změnit proměnné int na plovoucí desetinnou čárkou](./media/find-replace-control-animation.gif)

1. Znovu spusťte aplikaci kalkulačky a počet **42** číslem **119**.

   Všimněte si, že aplikace nyní vrací desítkových číslic namísto nula.

    ![Okna konzoly zobrazuje Kalkulačka aplikaci, která nyní vrací desetinná čísla v důsledku číslic.](./media/csharp-console-calculator-decimal.png)

Aplikace vytvoří však pouze desítkové výsledek. Vytvoříme několik další vylepšení kódu, tak, aby aplikace příliš vypočítat desetinná čísla.

1. Použití **najít a nahradit** ovládacího prvku (**Ctrl** + **F**) k změňte každou instanci `float` proměnnou `double`a každá změna instance `Convert.ToInt32` metodu `Convert.ToDouble`.

1. Spusťte aplikaci kalkulačky a počet **42,5** číslem **119.75**.

   Všimněte si, že aplikace nyní přijímá desetinné hodnoty a jako svůj výsledek vrátí delší desítkových číslic.

    ![Okno konzoly Kalkulačka aplikace, které nyní přijímá desetinná čísla a vrátí delší desítkových číslic ve výsledku](./media/csharp-console-calculator-usedecimals.png)

    (Počet desetinných míst v opravíme [revizi kódu](#revise-the-code) části.)

## <a name="debug-the-app"></a>Ladění aplikace

Vylepšili jsme v naší aplikaci základní kalkulačky, ale ještě nemá failsafes v místě pro zpracování výjimek, jako jsou chyby vstupu uživatele.

Například, pokud se pokusíte dělení čísla nulou nebo zadejte alfanumerického znaku při aplikace očekává, že číselný znak (nebo naopak), aplikace přestane fungovat a vrátí chybu.

Pojďme provede několik běžných chyby vstupu uživatele, vyhledejte v ladicím programu a opravte v kódu.

>[!TIP]
>Další informace o ladicím programu a jak to funguje, najdete v článku [první seznámení s ladicím programu sady Visual Studio](../../debugger/debugger-feature-tour.md) stránky.

### <a name="fix-the-divide-by-zero-error"></a>Opravte chybu "dělení nulou"

Při pokusu o dělení čísla nulou se zablokuje konzolovou aplikaci. Visual Studio pak se dozvíte, co je špatně v editoru kódu.

   ![Editor kódu sady Visual Studio zobrazí chybu dělení nulou](./media/csharp-console-calculator-dividebyzero-error.png)

Změňme kód pro zpracování této chyby.

1. Odstranit kód, který se zobrazí přímo mezi `case "d":` a komentář, který říká `// Wait for the user to respond before closing`.

1. Nahraďte ho následujícím kódem:

   ```csharp
            // Ask the user to enter a non-zero divisor until they do so
                while (num2 == 0)
                {
                    Console.WriteLine("Enter a non-zero divisor: ");
                    num2 = Convert.ToInt32(Console.ReadLine());
                }
                Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                break;
        }
    ```

   Poté, co přidáte kód do oddílu `switch` příkaz by měl vypadat podobně jako na následujícím snímku obrazovky:

   ![V části revidované "přepínač" v editoru kódu sady Visual Studio](./media/csharp-console-calculator-switch-code.png)

Nyní po libovolný počet dělení nulou, aplikace bude požádat o jiné číslo. Dokonce lepší: Nezpůsobí ukončení, s dotazem, dokud nezadáte jiné číslo než nula.

   ![Editor kódu sady Visual Studio zobrazí chybu dělení nulou](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>Opravte chyba "formát"

Pokud zadáte alfanumerického znaku při aplikace očekává, že číselný znak (nebo naopak), zablokuje aplikace konzoly. Visual Studio pak se dozvíte, co je špatně v editoru kódu.

   ![Editor kódu sady Visual Studio se zobrazí chyba formátu](./media/csharp-console-calculator-format-error.png)

Chcete-li vyřešit tuto chybu, jsme musí Refaktorovat kód, který jste dříve zadali.

#### <a name="revise-the-code"></a>Revizi kódu

Místo využívají `program` třídy pro zpracování veškerý kód, naší aplikace budeme budete rozdělit do dvou tříd: `calculator` a `program`.

`calculator` Třídy bude zpracovávat hromadné výpočtu práci a `program` třídy bude zpracovávat uživatelské rozhraní a zaznamenávání chyb práce.

Pusťme se do práce.

1. Vymazat úplně všechno *po* následující blok kódu:

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. V dalším kroku přidejte nový `calculator` třídy následujícím způsobem:

    ```csharp
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    ```

1. Pak přidejte novou `program` třídy následujícím způsobem:

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
    ```

1. Zvolte **Kalkulačka** ke spuštění programu, nebo stiskněte klávesu **F5**.

1. Postupujte podle zobrazených výzev a počet **42** číslem **119**. Vaše aplikace by měl vypadat nějak takto:

    ![Okno konzoly refaktorovaný kalkulačky aplikaci, která zahrnuje výzvy, na které akcí a zpracování chyb pro nesprávný vstupy](./media/csharp-console-calculator-refactored.png)

    Všimněte si, že máte možnost zadat další rovnice, dokud nezavřete konzolovou aplikaci. A omezili jsme také počet desetinných míst ve výsledku.

## <a name="close-the-app"></a>Zavřete aplikaci

1. Pokud jste tak již neučinili, zavřete aplikaci kalkulačku.

1. Zavřít **výstup** podokno v sadě Visual Studio.

   ![Zavřete podokno výstup v sadě Visual Studio](./media/csharp-calculator-close-output-pane.png)

1. V sadě Visual Studio, stiskněte klávesu **Ctrl**+**S** a uložte aplikaci.

1. Zavřete Visual Studio.

## <a name="code-complete"></a>Kód je kompletní

Během tohoto kurzu jsme spoustu změny do aplikace kalkulačku. Aplikace efektivněji nyní zpracovává výpočetní prostředky a zpracovává většinu chyby vstupu uživatele.

Tady je kompletní kód vše na jednom místě:

```csharp

using System;

namespace Calculator
{
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
}

```

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Další ještě více, pokračujte v následujících kurzech.

> [!div class="nextstepaction"]
> [Pokračovat s více C# kurzy](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>Viz také:

* [C# IntelliSense](../../ide/visual-csharp-intellisense.md)
* [Další informace k ladění C# kódu v sadě Visual Studio](tutorial-debugger.md)
