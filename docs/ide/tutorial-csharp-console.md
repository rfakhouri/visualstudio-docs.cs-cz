---
title: Začínáme s konzolové aplikace jazyka C# v sadě Visual Studio
description: Zjistěte, jak vytvořit konzolovou aplikaci C# v sadě Visual Studio, krok za krokem.
ms.custom: ''
ms.date: 10/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 3450572e4cf4959530599c5eea9efb3168485b58
ms.sourcegitcommit: 401be39a42ffe007593528b5bba62583ca9fcafd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2018
ms.locfileid: "50244369"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>Kurz: Začínáme s aplikaci konzoly C# v sadě Visual Studio

V tomto kurzu pro jazyk C#, budete používat Visual Studio k vytváření a spustíte aplikaci konzoly a prozkoumat některé funkce [sady Visual Studio integrované vývojové prostředí (IDE)](visual-studio-ide.md) při uděláte.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříme aplikaci projektu jazyka C#. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Potom zadejte název souboru *Kalkulačka*.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](../ide/media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>Přidat do pracovní skupiny (nepovinné)

Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro různé platformy .NET Core** pracovního vytížení. Přidejte tuto úlohu v jednom z následujících způsobů, v závislosti na tom, které jsou na vašem počítači nainstalovaná aktualizace sady Visual Studio 2017.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt

1. Zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Zvolte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/csharp-open-visual-studio-installer-generic-dark.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Použití nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogového okna a v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

## <a name="create-a-c-console-calculator-app"></a>Vytvoření aplikace "C# konzoly Kalkulačka"

1. Po vytvoření  **C# konzolovou aplikaci**, zadejte nebo vložte následující kód do editoru kódu:

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then instantiate to zero
                double num1 = 0; double num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToDouble(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToDouble(Console.ReadLine());

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
                        // Ask the user to enter a non-zero divisor until they do so
                        while (num2 == 0)
                        {
                            Console.WriteLine("Enter a non-zero divisor: ");
                            num2 = Convert.ToDouble(Console.ReadLine());
                        }
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                    // Return text for an incorrect option entry
                    default:
                        Console.WriteLine("That is an incorrect option entry, please try again.");
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```

   Kód, který se zobrazí po `static void Main(string[] args)` by měl vypadat jako na následujícím snímku obrazovky:

   ![Editor kódu znázorňující Kalkulačka konzoly C#](../ide/media/csharp-console-calculator-code.png)

1. Zvolte **Kalkulačka** ke spuštění programu, nebo stiskněte klávesu **F5**.

   ![Klikněte na tlačítko kalkulačky ke spuštění aplikace z panelu nástrojů](../ide/media/csharp-console-calculator-button.png)

1. Zobrazení vaší aplikace v okně konzoly. Když budete postupovat podle pokynů, vaše aplikace by měla vypadat podobně jako na následujícím snímku obrazovky:

    ![Kalkulačka aplikaci, která zahrnuje dotazování na akce, které se zobrazuje okno konzoly.](../ide/media/csharp-console-calculator.png)

### <a name="close-the-app"></a>Zavřete aplikaci

1. Stisknutím jakékoli klávesy zavřete aplikaci kalkulačku.

1. Zavřít **výstup** podokno v sadě Visual Studio.

   ![Zavřete podokno výstup v sadě Visual Studio](../ide/media/csharp-calculator-close-output-pane.png)

1. Zavřete Visual Studio.

## <a name="quick-answers-faq"></a>Rychlé odpovědi – nejčastější dotazy

Tady je rychlý – nejčastější dotazy ke zvýraznění některých klíčových koncepcí.

### <a name="what-is-c"></a>Co je C#?

C# je programovací jazyk zajišťující bezpečnost typů, která běží na rozhraní .NET Framework a .NET Core. Pomocí jazyka C# můžete vytvořit Windows aplikace, klient-server, databázové aplikace, XML webové služby, distribuované součásti a další.

### <a name="what-is-visual-studio"></a>Co je sada Visual Studio?

Visual Studio je integrované vývojové sady nástrojů podporujících produktivitu pro vývojáře. Si ho představit jako program, který můžete použít k vytvoření aplikací a aplikací.

### <a name="what-is-a-console-app"></a>Co je konzolová aplikace?

Konzolová aplikace přijímá vstupní a zobrazí výstup v okně příkazového řádku, označovaný také jako do konzoly.

### <a name="what-is-net-core"></a>Co je .NET Core?

.NET core je dalším krokem evoluční rozhraní .NET Framework. Pokud rozhraní .NET Framework umožňují sdílení kódu napříč programovacími jazyky, .NET Core přidává možnost sdílení kódu napříč platformami. Ještě lepší je open source.

(Rozhraní .NET Framework a .NET Core zahrnují knihovny předem připravených funkce. Zahrnují taky, že common language runtime (CLR), který se chová jako virtuální počítač, ve kterém se spustí váš kód.)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Další ještě více, pokračujte v následujících kurzech.

> [!div class="nextstepaction"]
> [Výukové programy jazyka C#](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>Viz také:

* [Základy C# pro naprosté začátečníky videokurz](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)
