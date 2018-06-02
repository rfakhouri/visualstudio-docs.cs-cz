---
title: Analyzovat data o využití procesoru (ASP.NET)
description: Měřit výkon aplikace v aplikacích ASP.NET pomocí diagnostického nástroje využití CPU
ms.custom: mvc
ms.date: 12/05/2017
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 00704c236e8e0c0453a36add4cb4603b76c31bd9
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477285"
---
# <a name="quickstart-analyze-cpu-usage-data-in-visual-studio-aspnet"></a>Rychlý úvod: Analyzujte data o využití procesoru v aplikaci Visual Studio (ASP.NET)

Visual Studio poskytuje mnoho výkonné funkce, které vám pomůžou analyzovat problémy s výkonem v aplikaci. Toto téma poskytuje rychlý způsob, jak další některé základní funkce. Zde podíváme na nástroj, který identifikovat kritická místa výkonu z důvodu vysoké využití procesoru. Diagnostické nástroje jsou podporované pro vývoj rozhraní .NET v sadě Visual Studio, včetně ASP.NET, nativního vývoje a vývoje v jazyce C++.

Diagnostické centrum nabízí řadu dalších možností, jak spustit a spravovat diagnostické relace. Pokud **využití procesoru** nástroj zde popsané nezískáte data, která budete potřebovat, [jiných nástrojů pro profilaci](../profiling/Profiling-Tools.md) poskytují různé druhy informace, které mohou být užitečné pro vás. V řadě případů může být kritickým bodem aplikace něco jiného než procesor, třeba paměť, vykreslování uživatelského rozhraní nebo dlouhá odezva síťového požadavku.

> [!NOTE]
> U platforem .NET Core a ASP.NET Core nástroj Využití procesoru v současnosti neposkytuje přesné výsledky o přenosných souborech PDB. Proto raději použijte celé soubory PDB.

## <a name="create-a-project"></a>Vytvoření projektu

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#**, zvolte **webové**a potom v prostředním podokně vyberte **webové aplikace ASP.NET (rozhraní .NET Framework)**.

    > [!NOTE]
    > Nástroj pro využití procesoru není aktuálně podporován v ASP.NET Core.

1. Zadejte název jako **MyProfilingApp_MVC** a klikněte na tlačítko **OK**.

1. V zobrazeném dialogu vyberte **MVC** v prostředním podokně a pak klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt. Průzkumník řešení (pravé podokno) ukazuje soubory projektu.

1. V Průzkumníku řešení klikněte pravým tlačítkem na složku modely a zvolte **přidat** > **třída**.

1. Pojmenujte novou třídu `Data.cs` a zvolte **přidat**.

1. V Průzkumníku řešení otevřete `Models/Data.cs` a přidejte následující `using` příkaz do horní části souboru:

    ```csharp
    using System.Threading;
    ```

1. V Data.cs nahraďte následujícím kódem:

    ```csharp
    public class Data
    {
    }
    ```

    s tímto kódem:

    ```csharp
    public class ServerClass
    {
        const int MIN_ITERATIONS = int.MaxValue / 1000;
        const int MAX_ITERATIONS = MIN_ITERATIONS + 10000;

        long m_totalIterations = 0;
        readonly object m_totalItersLock = new object();
        // The method that will be called when the thread is started.
        public void GenerateData()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            var x = GetNumber();
        }

        private int GetNumber()
        {
            var rand = new Random();
            var iters = rand.Next(MIN_ITERATIONS, MAX_ITERATIONS);
            var result = 0;
            lock (m_totalItersLock)
            {
                m_totalIterations += iters;
            }
            // we're just spinning here  
            // and using Random to frustrate compiler optimizations  
            for (var i = 0; i < iters; i++)
            {
                result = rand.Next();
            }
            return result;
        }
    }

    public class Simple
    {
        int numberOfThreads = 200;

        public Simple()
        {
            for (int i = 0; i < numberOfThreads; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.GenerateData));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }

        public int GetData()
        {
            // Not returning any meaningful data.
            return numberOfThreads;
        }
    }
    ```

1. V Průzkumníku řešení otevřete Controller/HomeControllers.cs a nahraďte následujícím kódem:

    ```csharp
    public ActionResult About()
    {
        ViewBag.Message = "Your application description page.";

        return View();
    }
    ```

    s tímto kódem:

    ```csharp
    public ActionResult About()
    {
        Models.Simple s = new Models.Simple();

        ViewBag.Message = "Your application description page.";

        return View(s.GetData());
    }
    ```

##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a>1. krok: Shromáždění profilačních dat 
  
1.  Nejdřív nastavit zarážky ve vaší aplikaci tento řádek kódu `Simple` konstruktor:

    `for (int i = 0; i < 200; i++)`

    Nastavte zarážky kliknutím v mřížky doleva řádek kódu.

1.  V dalším kroku nastavení druhý zarážky na pravé složené závorce na konci `Simple` konstruktor:

     ![Nastavit zarážky pro profilaci](../profiling/media/quickstart-cpu-usage-breakpoints-aspnet.png)

    > [!TIP]
    > Nastavením dvou zarážek omezíte shromažďování dat jenom na analyzovanou část kódu.
  
1.  **Diagnostické nástroje** okno již viditelné, pokud jste vypnuli ho. Pokud ho chcete znovu zobrazit, klikněte na **Ladit / Okna / Zobrazit diagnostické nástroje**.

1.  Klikněte na **Ladit / Spustit ladění** (nebo na panelu nástrojů stiskněte **Start** nebo **F5**).

1.  Když aplikace dokončí načítání, klikněte na **o** odkaz v horní části webové stránky spustit nový kód.

1.  Podívejte se na **Souhrn** diagnostické nástroje se zobrazí.

1.  Při ladicího programu je pozastavena, povolení shromažďování těchto dat o využití procesoru výběrem **záznam procesoru profil**a pak otevřete **využití procesoru** kartě.

     ![Diagnostické nástroje povolit procesoru profilace](../profiling/media/quickstart-cpu-usage-summary.png)

     Pokud je povoleno shromažďování dat, zobrazí tlačítko záznam červeném kroužku.

     Pokud vyberete **záznam procesoru profil**, Visual Studio bude nahráváním funkcí a jak dlouho budou chtít provést a také poskytuje časová osa grafu, můžete se zaměřit na konkrétní segmenty relace vzorkování. Tato shromážděná data můžete zobrazit, jenom když aplikace se zastavilo na zarážce.

6.  Stiskněte klávesu F5, kterou spustíte aplikaci až ke druhé zarážce.

     Teď máte údaje o výkonu aplikace přesně pro oblast kódu spuštěnou mezi dvěma zarážkami.

     Profiler začne připravovat údaje o vlákně. Počkejte, až skončí.
  
     V nástroji Využití procesoru se na kartě **Využití procesoru** zobrazí sestava.

     Teď můžete začít analyzovat data.

## <a name="Step2"></a> 2. krok: Analýza dat o využití procesoru

Analýzu dat doporučujeme začít tím, že zkontrolujete seznam funkcí na kartě Využití procesoru. Zjistěte nejaktivnější funkce a pak se na každou z nich podívejte podrobněji.

1. V seznamu funkcí se podívejte, jaké funkce vykonávají většinu práce.

     ![Diagnostické nástroje karta využití procesoru](../profiling/media/quickstart-cpu-usage-cpu-aspnet.png)

    > [!TIP]
    > Funkce jsou seřazené od nejvíce pracujících po nejméně pracující (nejsou seřazené podle pořadí, v jakém byly volány). Pomůže vám to rychle identifikovat funkce, které běží nejdéle.

2. V seznamu funkce dvakrát klikněte `MyProfilingApp_MVC.Models.ServerClass::GetNumber` funkce.

    Když dvakrát kliknete funkce **volající/volaný** zobrazení se otevře v levém podokně. 

    ![Diagnostické nástroje volající volaný – zobrazení](../profiling/media/quickstart-cpu-usage-caller-callee-aspnet.png)

    V tomto zobrazení vybrané funkce se zobrazí v záhlaví a v **aktuální funkce** pole (`ServerClass::GetNumber`, v tomto příkladu). Funkce, která volala aktuální funkci, se zobrazí vlevo v části **Volající funkce** a všechny funkce volané aktuální funkcí se zobrazí vpravo v poli **Volané funkce**. (Pokud chcete aktuální funkci změnit, vyberte libovolné pole.)

    V tomto zobrazení vidíte celkový čas (ms) a procento z celkové doby spuštění aplikace, kterou funkce potřebovala k dokončení.

    **Tělo funkce** také zobrazuje celkovou dobu (a procento času) spotřebovanou tělem funkce, ale bez doby spotřebované volajícími a volanými funkcemi. (V tomto obrázku byly tělo funkce a zbývající čas strávený 2220 mimo 2235 ms (< 20 ms) byl stráven v externí kódu volaného pomocí této funkce). Skutečné hodnoty se liší v závislosti na vašem prostředí.

    > [!TIP]
    > Vysoké hodnoty v **těle funkce** pravděpodobně znamenají kritické místo výkonu samotné funkce.

## <a name="next-steps"></a>Další kroky

- [Analýza využití paměti](../profiling/memory-usage.md)identifikovat kritická místa výkonu.
- [Analýza využití procesoru](../profiling/cpu-usage.md) podrobnější informace o nástroji využití procesoru.
- Analýza využití procesoru bez připojit ladicí program nebo cílením spuštěné aplikaci - Další informace najdete v tématu [shromažďování dat profilaci bez ladění](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) v [spustit profilování nástroje s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Viz také  

 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md)
