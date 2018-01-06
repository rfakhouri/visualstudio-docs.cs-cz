---
title: "Analyzovat data o využití procesoru (spravovaný kód) | Microsoft Docs"
ms.custom: 
ms.date: 12/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 50f2612687a58857f4d05478db073070e2cc9936
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="analyze-cpu-usage-data-in-visual-studio-managed-code"></a>Analyzovat data o využití procesoru v sadě Visual Studio (spravovaný kód)

Visual Studio poskytuje mnoho výkonné funkce, které vám pomůžou analyzovat problémy s výkonem v aplikaci. Toto téma poskytuje rychlý způsob, jak další některé základní funkce. Zde podíváme na nástroj, který identifikovat kritická místa výkonu z důvodu vysoké využití procesoru. Diagnostické nástroje jsou podporované pro .NET – vývoj v sadě Visual Studio, včetně ASP.NET a pro vývoj nativní/C++.

Centrum diagnostiky nabízí mnoho dalších možností spouštět a spravovat relace diagnostiky. Pokud **využití procesoru** nástroj zde popsané nezískáte data, která budete potřebovat, [jiných nástrojů pro profilaci](../profiling/profiling-feature-tour.md) poskytují různé druhy informace, které mohou být užitečné pro vás. V mnoha případech kritická místa výkonu aplikace může být způsobeno něco jiného než procesoru, jako je například paměť, vykreslování uživatelského rozhraní nebo doba požadavku sítě. Centrum diagnostiky nabízí spoustu dalších možností zaznamenávat a analyzovat tento druh data.

## <a name="create-a-project"></a>Vytvoření projektu

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

2. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **Windows Classic Desktop**a potom v prostředním podokně vyberte **konzolovou aplikaci (rozhraní .NET Framework)**.

3. Zadejte název jako **MyProfilerApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

2. Otevřete Program.cs a všechny kódu nahraďte následujícím kódem:

    ```cs
    using System;
    using System.Threading;
    public class ServerClass
    {
        const int MIN_ITERATIONS = int.MaxValue / 1000;
        const int MAX_ITERATIONS = MIN_ITERATIONS + 10000;
    
        long m_totalIterations = 0;
        readonly object m_totalItersLock = new object();
        // The method that will be called when the thread is started.
        public void DoWork()
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
        public static void Main()
        {
            for (int i = 0; i < 200; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();
    
            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.DoWork));
            // Start the thread.
            InstanceCaller.Start();
    
            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");
    
        }
    }
    ```

    ```vb
    Imports System
    Imports System.Threading
    
    Namespace MyProfilerApp
        Public Class ServerClass
            Const MIN_ITERATIONS As Integer = Integer.MaxValue / 1000
            Const MAX_ITERATIONS As Integer = MIN_ITERATIONS + 10000
    
            Private m_totalIterations As Long = 0
            ReadOnly m_totalItersLock As New Object()
            ' The method that will be called when the thread is started.
            Public Sub DoWork()
                Console.WriteLine("ServerClass.InstanceMethod is running on another thread.")
    
                Dim x = GetNumber()
            End Sub
    
            Private Function GetNumber() As Integer
                Dim rand = New Random()
                Dim iters = rand.[Next](MIN_ITERATIONS, MAX_ITERATIONS)
                Dim result = 0
                SyncLock m_totalItersLock
                    m_totalIterations += iters
                End SyncLock
                ' we're just spinning here  
                ' and using Random to frustrate compiler optimizations  
                For i As Integer = 0 To iters - 1
                    result = rand.[Next]()
                Next
                Return result
            End Function
        End Class
    
        Public Class Simple
            Public Shared Sub Main()
                For i As Integer = 0 To 199
                    CreateThreads()
                Next
            End Sub
            Public Shared Sub CreateThreads()
                Dim serverObject As New ServerClass()
    
                Dim InstanceCaller As New Thread(New ThreadStart(AddressOf serverObject.DoWork))
                ' Start the thread.
                InstanceCaller.Start()
    
                Console.WriteLine("The Main() thread calls this after " + "starting the new InstanceCaller thread.")
    
            End Sub
        End Class
    End Namespace
    ```

    > [!NOTE]
    > V jazyce Visual Basic, ujistěte se objekt spuštění je nastavena na `Sub Main` (**vlastnosti > aplikace > spouštěcí objekt**).

##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a>Krok 1: Shromáždění data profilování 
  
1.  Nejdřív nastavit zarážky ve vaší aplikaci tento řádek kódu `Main` funkce:

    `for (int i = 0; i < 200; i++)`

    nebo v jazyce Visual Basic:

    `For i As Integer = 0 To 199`

    Nastavte zarážky kliknutím v mřížky doleva řádek kódu.

2.  V dalším kroku nastavení druhý zarážky na pravé složené závorce na konci `Main` funkce:

     ![Nastavte zarážky pro profilace](../profiling/media/quickstart-cpu-usage-breakpoints.png "nastavit zarážky pro profilaci")

    > [!TIP]
    > Nastavením dvě zarážky můžete omezit shromažďování dat na části kódu, který chcete analyzovat.
  
3.  **Diagnostické nástroje** okno již viditelné, pokud jste vypnuli ho. Zobrazte okno znovu, klikněte na tlačítko **ladění / Windows / zobrazit diagnostické nástroje**.

4.  Klikněte na tlačítko **ladění / spusťte ladění** (nebo **spustit** na panelu nástrojů nebo **F5**).

     Po dokončení načítání, aplikace **Souhrn** diagnostické nástroje se zobrazí.

5.  Při ladicího programu je pozastavena, povolení shromažďování těchto dat o využití procesoru výběrem **záznam procesoru profil**a pak otevřete **využití procesoru** kartě.

     ![Diagnostické nástroje povolit profilace procesoru](../profiling/media/quickstart-cpu-usage-summary.png "diagnostické nástroje povolit procesoru profilace")

     Pokud je povoleno shromažďování dat, zobrazí tlačítko záznam červeném kroužku.

     Pokud vyberete **záznam procesoru profil**, Visual Studio bude nahráváním funkcí a jak dlouho budou chtít provést a také poskytuje časová osa grafu, můžete se zaměřit na konkrétní segmenty relace vzorkování. Tato shromážděná data můžete zobrazit, jenom když aplikace se zastavilo na zarážce.

6.  Stiskněte F5 a spusťte aplikaci k vaší zarážce druhý.

     Nyní nyní máte údaje o výkonu pro vaši aplikaci speciálně pro oblast kód, který běží mezi dvěma zarážky.

     Profileru začne přípravu dat přístup z více vláken. Počkejte na její dokončení.
  
     Zobrazí sestavu v nástroj využití procesoru **využití procesoru** kartě.

     V tomto okamžiku můžete začít analyzovat data.

## <a name="Step2"></a>Krok 2: Analyzovat data o využití procesoru

Doporučujeme začít analýza dat kontrolou seznamu funkcí podle využití procesoru, určení funkcí, které pracujeme na maximum a pak trvá bližší pohled na každé z nich.

1. V seznamu funkce zkontrolujte funkce, které pracujeme na maximum.

     ![Diagnostické nástroje využití CPU karta](../profiling/media/quickstart-cpu-usage-cpu.png "DiagToolsCPUUsageTab")

    > [!TIP]
    > Funkce jsou uvedeny v pořadí od těch, které nejvíce pracuje (nejsou v pořadí volání). Díky tomu můžete rychle zjistit nejdelší spuštěné funkce.

2. V seznamu funkce dvakrát klikněte `ServerClass::GetNumber` funkce.

    Když dvakrát kliknete funkce **volající/volaný** zobrazení se otevře v levém podokně. 

    ![Diagnostické nástroje volající volaný – zobrazení](../profiling/media/quickstart-cpu-usage-caller-callee.png "DiagToolsCallerCallee")

    V tomto zobrazení vybrané funkce se zobrazí v záhlaví a v **aktuální funkce** pole (`GetNumber`, v tomto příkladu). Funkce, která volá funkci current se zobrazí na levé straně v části **volání funkce**, a všechny funkce volá funkci current se zobrazují v **volat funkce** pole na pravé straně. (Můžete vybrat buď použijte ke změně aktuální funkce.)

    Toto zobrazení uvádí celkový čas (ms) a procento celkového aplikaci spuštěnou dobu, po kterou funkce provedlo v návaznosti na Dokončit.

    **Funkce text** také ukazuje celkové množství času (a procentuální hodnotu času) věnovaný tělo funkce bez doby věnovaný volání a funkce s názvem. (V tomto obrázku byly tělo funkce a zbývající čas strávený 2856 mimo 2863 ms (< 20 ms) byl stráven v externí kódu volaného pomocí této funkce). Skutečné hodnoty se liší v závislosti na vašem prostředí.

    > [!TIP]
    > Vysoce hodnoty v **tělo funkce** může znamenat přetížení v rámci funkce sám sebe.

## <a name="next-steps"></a>Další kroky

- [Analýza využití paměti](../profiling/memory-usage.md)identifikovat kritická místa výkonu.
- [Analýza využití procesoru](../profiling/cpu-usage.md) podrobnější informace o nástroji využití procesoru.
- Analýza využití procesoru bez připojit ladicí program nebo cílením spuštěné aplikaci - Další informace najdete v tématu [shromažďování dat profilaci bez ladění](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) v [spustit profilování nástroje s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Viz také  

 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md)
