---
title: Další informace k ladění pomocí ladicího programu sady Visual Studio
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 08/01/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4534db0f4e85cda2cb3f0c45fdd57e768fa75ab1
ms.sourcegitcommit: 40b6438b5acd7e59337a382c39ec711b9e99cc8a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/11/2018
ms.locfileid: "49101040"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>Kurz: Zjistěte, jak ladit pomocí sady Visual Studio

Tento článek obsahuje představení funkcí v ladicím programu sady Visual Studio podrobného návodu. Pokud potřebujete vyšší úroveň zobrazení funkcí ladicího programu, [prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md). Pokud jste *ladění aplikace*, obvykle to znamená, že spustíte aplikaci s připojeným ladícím nástrojem. Když toto provedete, ladicí program poskytuje mnoho způsobů, jak zjistit, co kód dělá, při spuštění. Můžete procházet kódem a podívejte se na hodnoty uložené v proměnné, můžete nastavit hodinky na proměnné zobrazíte, když se změní hodnoty, můžete prozkoumat cesta provedení kódu naleznete v tématu, jestli větev kódu je spuštěná, a tak dále. Pokud je to poprvé, kterou jste se pokusili ladění kódu, můžete chtít číst [ladění pro naprosté začátečníky](../debugger/debugging-absolute-beginners.md) před provedením tohoto článku.

|         |         |
|---------|---------|
|  ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video")  |    [Podívejte se na video](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) ladění, která zobrazuje podobný postup. |

Přestože je ukázkovou aplikaci C# a C++, funkce platí pro Visual Basic, JavaScript a jinými jazyky podporovanými sady Visual Studio (Pokud není uvedeno jinak). Snímky obrazovky jsou v jazyce C#.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Spuštění ladicího programu a dosažení zarážky.
> * Další příkazy ke krokování kódu v ladicím programu
> * Kontrolovat proměnné v datových tipech a okno ladicího programu
> * Prozkoumat zásobník volání

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio 2017 a **vývoj desktopových aplikací .NET** nebo **vývoj desktopových aplikací pomocí C++** pracovního vytížení.

    Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

    Pokud je potřeba, nainstalujte úlohu, ale už máte sadu Visual Studio, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno (vyberte **souboru**  >  **Nové** > **projektu**). Spustí se instalační program pro Visual Studio. Vyberte. **.NET desktop development** nebo **vývoj desktopových aplikací pomocí C++** úloh, klikněte na tlačítko **změnit**.

## <a name="create-a-project"></a>Vytvoření projektu

1. V sadě Visual Studio, zvolte **soubor > Nový projekt**.

2. V části **Visual C#** nebo **Visual C++**, zvolte **Windows Desktop**a potom v prostředním podokně vyberte **konzolovou aplikaci** ( **Windows konzolovou aplikaci** v jazyce C++).

    Pokud se nezobrazí **konzolovou aplikaci** šablony projektu, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Zvolte *vývoj desktopových aplikací .NET** nebo **vývoj desktopových aplikací pomocí C++** úloh, klikněte na tlačítko **změnit**.

3. Zadejte název, například **get spuštění – ladění** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

    > [!NOTE]
    > Chcete-li přepnout mezi C# a C++ ukázkový kód v tomto článku pomocí filtru jazyk v pravém horním rohu této stránky.

4. V *Program.cs* (C#) nebo *get spuštění debugging.cpp* (C++), nahraďte následující kód

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;

    namespace get_started_debugging
    {
        class Program
        {
            static void Main(string[] args)
            {
            }
        }
    }
    ```

    ```c++
    int main()
    {
        return 0;
    }
    ```

    s tímto kódem:

    ```csharp
    using System;
    using System.Collections.Generic;

    public class Shape
    {
        // A few example members
        public int X { get; private set; }
        public int Y { get; private set; }
        public int Height { get; set; }
        public int Width { get; set; }
   
        // Virtual method
        public virtual void Draw()
        {
            Console.WriteLine("Performing base class drawing tasks");
        }
    }

    class Circle : Shape
    {
        public override void Draw()
        {
            // Code to draw a circle...
            Console.WriteLine("Drawing a circle");
            base.Draw();
        }
    }

    class Rectangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a rectangle...
            Console.WriteLine("Drawing a rectangle");
            base.Draw();
        }
    }

    class Triangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a triangle...
            Console.WriteLine("Drawing a trangle");
            base.Draw();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {

            var shapes = new List<Shape>
            {
                new Rectangle(),
                new Triangle(),
                new Circle()
            };

            foreach (var shape in shapes)
            {
                shape.Draw();
            }

            // Keep the console open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }

    }

    /* Output:
        Drawing a rectangle
        Performing base class drawing tasks
        Drawing a triangle
        Performing base class drawing tasks
        Drawing a circle
        Performing base class drawing tasks
    */
    ```

    ```c++
    #include "pch.h"

    #include <string>
    #include <vector>
    #include <iostream>

    class Shape
    {
        int privateX = 0;
        int privateY = 0;
        int privateHeight = 0;
        int privateWidth = 0;

        int getX() const { return privateX; }
        void setX(int value) { privateX = value; }

        int getY() const { return privateY; }
        void setY(int value) { privateY = value; }

        int getHeight() const { return privateHeight; }
        void setHeight(int value) { privateHeight = value; }

        int getWidth() const { return privateWidth; }
        void setWidth(int value) { privateWidth = value; }

        public:
        // Virtual method
        virtual void Draw()
        {
            std::wcout << L"Performing base class drawing tasks" << std::endl;
        }
    };

    class Circle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a circle...
        std::wcout << L"Drawing a circle" << std::endl;
        Shape::Draw();
        }
    };

    class Rectangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a rectangle...
        std::wcout << L"Drawing a rectangle" << std::endl;
        Shape::Draw();
        }
    };

    class Triangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a triangle...
        std::wcout << L"Drawing a trangle" << std::endl;
        Shape::Draw();
        }
    };

    int main(std::vector<std::wstring> &args)
    {
        auto shapes = std::vector<Shape*>
        {
            new Rectangle(),
            new Triangle(),
            new Circle()
        };

        for (auto shape : shapes)
        {
            shape->Draw();
        }
    }

    /* Output:
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    */
    ```

## <a name="start-the-debugger"></a>Spuštění ladicího programu!

1. Stisknutím klávesy **F5** (**ladit > Spustit ladění**) nebo **spustit ladění** tlačítko ![spustit ladění](../debugger/media/dbg-tour-start-debugging.png "spustit ladění ") na panelu nástrojů ladění.

     **F5** spustí aplikaci se ladicí program připojen k aplikaci zpracování, ale v tuto chvíli jsme neprovedli nic zvláštního prozkoumat kód. Proto pouze načítání aplikace a zobrazí výstup konzoly.

    ```
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    ```

     V tomto kurzu vytvoříme podrobněji podíváme na tuto aplikaci pomocí ladicího programu a získejte funkce, podívejte se na ladicí program.

2. Zastavení ladicího programu stisknutím klávesy red stop ![Zastavit ladění](../debugger/media/dbg-tour-stop-debugging.png "Zastavit ladění") tlačítko.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Nastavte zarážku a spuštění ladicího programu

1. V `foreach` smyčku z `Main` – funkce (`for` smyčky v jazyce C++ `main` funkce), nastavte zarážku kliknutím na levém okraji následující řádek kódu:

    `shape.Draw()` (nebo `shape->Draw()` v jazyce C++)

    Se zobrazí červený kruh, kde nastavit zarážku.

    Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští. 

6. Stisknutím klávesy **F5** nebo **spustit ladění** tlačítko, aplikace se spustí, a ladicí program běží na řádek kódu, kde nastavit zarážku.

    ![Nastavte a použijte zarážku](../debugger/media/get-started-set-breakpoint.gif)

    Žlutá šipka označuje příkaz na které ladicí program pozastaví, což také pozastaví provádění aplikace na stejném místě (Tento příkaz nebyl dosud proveden).

     Pokud ještě není aplikace spuštěna, **F5** spustí ladicí program a k první zarážce se zastaví. V opačném případě **F5** bude pokračovat spuštěním aplikace až k další zarážce.

    Zarážky jsou užitečná funkce, když znáte řádek kódu nebo části kódu, který chcete prozkoumat podrobněji.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Vyhledání kódu v ladicím programu pomocí příkazů kroku

Většinou, klávesové zkratky tady používáme, protože je dobrým způsobem, jak získat rychlé při spuštění aplikace v ladicím programu (ekvivalentní příkazy jako je například nabídka příkazy jsou uvedeny v závorkách).

1. Během pozastavení v `shape.Draw` volání metody `Main` – metoda (`shape->Draw` v jazyce C++), stiskněte klávesu **F11** (nebo zvolte **ladit > Krokovat s vnořením**) pro přechod do kódu pro `Rectangle` Třída.

     ![Můžete krokovat s vnořením kód F11](../debugger/media/get-started-f11.png "F11 Krokovat s vnořením")

     Je F11 **Krokovat s vnořením** příkazu a posune jeden příkaz spuštění aplikace v čase. F11 je dobrým způsobem, jak prozkoumat provádění toku v nejvíce podrobností. (Rychlejší procházení kódu, ukážeme vám několik možností také.) Ve výchozím nastavení, ladicí program přeskočí neuživatelském kódu (Pokud potřebujete další podrobnosti, [pouze můj kód](../debugger/just-my-code.md)).

2. Stisknutím klávesy **F10** (nebo zvolte **ladit > Krokovat s přeskočením**) několikrát, dokud ladicí program se zastaví na `base.Draw` volání metody (`Shape::Draw` v jazyce C++) a potom stiskněte klávesu **F10** ještě jednou.

     ![F10 můžete krokovat s přeskočením kód](../debugger/media/get-started-step-over.png "F10 Krokovat s přeskočením")

     Všimněte si, že tento čas, který ladicí program Nekrokovat s vnořením do `Draw` metody základní třídy (`Shape`). **F10** přejde ladicí program bez krokování do funkce nebo metody v kódu vaší aplikace (kód stále provádí). Stisknutím klávesy F10 na `base.Draw` (nebo `Shape::Draw`) volání metody (místo **F11**), jsme přeskočil implementační kód pro `base.Draw` (které možná jsme nejsou nyní zájem).

## <a name="navigate-code-using-run-to-click"></a>Vyhledání kódu pomocí běžet do kliknutí

5. V editoru kódu, přejděte dolů a najeďte myší `Console.WriteLine` – metoda (`std::cout` v jazyce C++) v `Triangle` třídy do zelené **běžet do kliknutí** tlačítko ![běžet do kliknutí](../debugger/media/dbg-tour-run-to-click.png " RunToClick") se zobrazí na levé straně.

     ![Použít Run to Click funkce](../debugger/media/get-started-run-to-click.png "běžet do kliknutí")

    >  [!NOTE]
    > **Běžet do kliknutí** je novinkou systémů tlačítko [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]. Pokud nevidíte tlačítko zelenou šipku, použijte **F11** v tomto příkladu místo toho k přechodu na správném místě ladicí program.

6. Klikněte na tlačítko **běžet do kliknutí** tlačítko ![běžet do kliknutí](../debugger/media/dbg-tour-run-to-click.png "RunToClick").

    Pomocí tohoto tlačítka je podobné nastavení dočasné zarážky. **Běžet do kliknutí** je užitečné pro rychlé navigace v rámci viditelné oblasti kódu aplikace (můžete kliknout na jakékoli otevření souboru).

    Ladicí program přejde `Console.WriteLine` implementace metody pro `Triangle` třídy (`std::cout` v jazyce C++).

    Během pozastavení, si všimnete překlep! Je zadáno chybně výstupu "Kreslení trangle". Jsme tady ho můžou opravit při spuštění aplikace v ladicím programu.

## <a name="edit-code-and-continue-debugging"></a>Úprava kódu a pokračování ladění

1. Klikněte na tlačítko do "Kreslení trangle" a zadejte opravu, změna "trangle" na "trojúhelník".

1. Stisknutím klávesy **F11** jednou a můžete zobrazit znovu přejde ladicí program.

    > [!NOTE]
    > V závislosti na tom, jaký typ kódu upravit v ladicím programu může se zobrazit zpráva upozornění. V některých případech kód potřeba překompilovat, než budete moct pokračovat.

## <a name="step-out"></a>Krokovat s Vystoupením

Řekněme, že skončíte zkoumání `Draw` metodu `Triangle` třídy a chcete využít funkce ale zůstávají v ladicím programu. Můžete provést pomocí **Krokovat s Vystoupením** příkazu.

1. Stisknutím klávesy **Shift** + **F11** (nebo **ladit > Krokovat s Vystoupením**).

     Tento příkaz pokračuje v provádění aplikace (a přejde ladicí program) až do aktuálního funkce vrátí.

     Měli byste se vrátit `foreach` smyčky v `Main` – metoda (`for` smyčky v jazyce C++).

## <a name="restart-your-app-quickly"></a>Rychlé restartování aplikace

Klikněte na tlačítko **restartovat** ![restartovat aplikaci](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítko na panelu nástrojů ladění (**Ctrl** + **Shift**   +  **F5**).

Když stisknete klávesu **restartovat**, šetří čas a zastavuje se aplikace a restartování ladicího programu. Ladicí program pozastaví na první zarážce, kterou dosáhnete spuštěním kódu.

Ladicí program se znovu zastaví na zarážce, nastavíte na `shape.Draw()` – metoda (`shape->Draw()` v jazyce C++).

## <a name="inspect-variables-with-data-tips"></a>Kontrolovat proměnné s datových tipech

Funkce, které umožňují kontrolovat proměnné jsou jedním z nejužitečnějších funkce ladicího programu, a to různými způsoby. Při pokusu o ladění chyby se často, pokoušíte zjistit, zda jsou proměnné ukládání hodnot, které očekáváte, že ho, aby v určitou dobu.

1. Během pozastavení na `shape.Draw()` – metoda (`shape->Draw()` v jazyce C++), najeďte myší `shapes` objektu a zobrazit její hodnotu vlastnosti výchozí `Count` vlastnost.

1. Rozbalte `shapes` objektu zobrazíte všechny její vlastnosti, jako je například první index pole `[0]`, který má hodnotu `Rectangle` (C#) nebo adresu paměti (C++).

     ![Zobrazení datového tipu](../debugger/media/get-started-data-tip.gif "zobrazení popisu dat.")

    Můžete dále rozšířit objekty zobrazení jejich vlastností, jako `Height` vlastnosti obdélníku.

    Často při ladění, chcete rychle zkontrolovat hodnoty vlastností pro objekty a datové tipy jsou dobrým způsobem, jak to udělat.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Kontrolovat proměnné s okna Automatické hodnoty a místní hodnoty

1. Podívejte se na **automatické hodnoty** okno v dolní části editoru kódu.

     ![Kontrolovat proměnné v okně Automatické hodnoty](../debugger/media/get-started-autos-window.png "okno Automatické hodnoty")

    V **automatické hodnoty** okně se zobrazí proměnné a jejich aktuální hodnoty. **Automatické hodnoty** okně se zobrazí všechny proměnné používané v aktuálním řádkem nebo předchozí řádku (v jazyce C++, v okně se zobrazí proměnné v předchozí tři řádky kódu. V dokumentaci pro konkrétní jazyk chování).

    > [!NOTE]
    > V jazyce JavaScript **lokální** okna je ale není podporován **automatické hodnoty** okna.

2. Dále, podívejte se na **lokální** okno na kartě vedle **automatické hodnoty** okna.

    **Lokální** v okně se zobrazí proměnné, které jsou v aktuálním [oboru](https://www.wikipedia.org/wiki/Scope_(computer_science)).

## <a name="set-a-watch"></a>Nastavení sledování

1. V okně editoru hlavní kód, klikněte pravým tlačítkem myši `shapes` objektu a zvolte **Přidat kukátko**.

    **Watch** otevře se okno v dolní části editoru kódu. Můžete použít **Watch** okno zadat proměnné (nebo výraz), který chcete sledovat.

    Teď máte nastavit na sledování `shapes` objekt kde můžete zobrazit její hodnotu změnit při procházení ladicí program. Na rozdíl od jiných proměnných oknech **Watch** okno vždy zobrazuje proměnné, že se díváte (jsou sice zobrazené šedě, když mimo rozsah).

## <a name="examine-the-call-stack"></a>Prozkoumat zásobník volání

1. Během pozastavení v `foreach` smyčky (`for` smyčky v jazyce C++), klikněte na tlačítko **zásobník volání** okna, která je ve výchozím nastavení, otevřete v pravém dolním podokně.

1. Klikněte na tlačítko **F11** několikrát, dokud se nezobrazí pozastavení v ladicím programu `Circle.Draw` metody v editoru kódu. Podívejte se na **zásobník volání** okna.

    ![Prozkoumat zásobník volání](../debugger/media/get-started-call-stack.png "ExamineCallStack")

    **Zásobník volání** okno zobrazuje pořadí, ve kterém jsou získávání volány metody a funkce. Na horní zobrazený řádek zobrazuje aktuální funkci ( `Circle.Draw` nebo `Circle::Draw` metody v této aplikaci). Druhý řádek ukazuje, že `Circle.Draw` byla volána `Main` – metoda (`main` v jazyce C++), a tak dále.

    >  [!NOTE]
    > **Zásobník volání** okno je podobné ladění perspektivy v některých prostředí IDE, jako je Eclipse.

    Zásobník volání je dobrým způsobem, jak zkoumat a pochopit provádění toku aplikace.

    Dvojitým kliknutím na řádek kódu go, podívejte se na tento zdrojový kód a také změny v aktuálním oboru kontrolován ladicím programem. Tato akce nepřesouvejte vpřed ladicí program.

    Můžete také použít nabídek klikněte pravým tlačítkem **zásobník volání** okno a dělat jiné věci. Například vložení do určené funkce zarážky, ladicí program pomocí předem **spustit ke kurzoru**a zkontrolujte zdrojový kód. Další informace najdete v tématu [postupy: prozkoumání zásobník volání](../debugger/how-to-use-the-call-stack-window.md).

## <a name="change-the-execution-flow"></a>Změna toku provádění

1. Pomocí ladicího programu v pozastavena `Circle.Draw` volání metody, stiskněte klávesu **F11** několikrát, dokud ladicí program pozastaví na `base.Draw` volání metody (`Shape::Draw` v jazyce C++).

1. Pomocí myši žlutá šipka (spuštění ukazatele) na levé straně vzít a přesunout žlutou šipku na jeden řádek nahoru `Console.WriteLine` (`std::cout` v jazyce C++) volání metody.

1. Stisknutím klávesy **F11** ještě jednou.

    Znovu spustí ladicí program `Console.WriteLine` – metoda (`std::cout` v jazyce C++).

    Změnou provádění toku můžete provést kroky, jako je test cesty spuštění odlišný kód nebo znovu spustit kód bez restartování ladicího programu.

    > [!WARNING]
    > Často je potřeba pečlivě s touto funkcí a zobrazit upozornění v popisu. Příliš se může zobrazit další varování. Ukazatele nejde vrátit zpět aplikaci do předchozího stavu aplikace.

1. Stisknutím klávesy **F5** bude moct být spuštěná aplikace.

    Blahopřejeme k dokončení tohoto kurzu!

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak spustit ladicí program, krokovat kód a můžete kontrolovat proměnné. Můžete chtít získat podrobný přehled funkcí ladicího programu spolu s odkazy na další informace.

> [!div class="nextstepaction"]
> [Tipy a triky pro ladicí program](../debugger/debugger-tips-and-tricks.md)
