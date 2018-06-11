---
title: Analyzovat data o využití procesoru (C++)
description: Měřit výkon aplikace v jazyce C++ pomocí diagnostického nástroje využití CPU
ms.custom: ''
ms.date: 12/05/2017
ms.technology: vs-ide-debug
ms.topic: quickstart
f1_keywords:
- ''
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 674c7f30a325c8d615c76a784b3c4e80e306ead6
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256234"
---
# <a name="quickstart-analyze-cpu-usage-data-in-visual-studio-c"></a>Rychlý úvod: Analyzujte data o využití procesoru v aplikaci Visual Studio (C++)

Visual Studio poskytuje mnoho výkonné funkce, které vám pomůžou analyzovat problémy s výkonem v aplikaci. Toto téma poskytuje rychlý způsob, jak další některé základní funkce. Zde podíváme na nástroj, který identifikovat kritická místa výkonu z důvodu vysoké využití procesoru. Diagnostické nástroje jsou podporované pro vývoj rozhraní .NET v sadě Visual Studio, včetně ASP.NET, nativního vývoje a vývoje v jazyce C++.

Diagnostické centrum nabízí řadu dalších možností, jak spustit a spravovat diagnostické relace. Pokud **využití procesoru** nástroj zde popsané nezískáte data, která budete potřebovat, [jiných nástrojů pro profilaci](../profiling/profiling-feature-tour.md) poskytují různé druhy informace, které mohou být užitečné pro vás. V řadě případů může být kritickým bodem aplikace něco jiného než procesor, třeba paměť, vykreslování uživatelského rozhraní nebo dlouhá odezva síťového požadavku. Diagnostické centrum nabízí řadu dalších možností, jak data tohoto druhu zaznamenávat a analyzovat.

## <a name="create-a-project"></a>Vytvoření projektu

1. V sadě Visual Studio, vyberte **soubor**>**nový projekt**.

2. V části **Visual C++**, zvolte **Windows Desktop**a potom v prostředním podokně vyberte **konzolové aplikace pro Windows**.

3. Zadejte název jako **Diagnostics_Get_Started_Native** a klikněte na tlačítko **OK**.

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
    #include <iostream>
    #include <limits>
    #include <mutex>
    #include <random>
    #include <functional>
    
    //.cpp file code:
    
    static constexpr int MIN_ITERATIONS = std::numeric_limits<int>::max() / 1000;
    static constexpr int MAX_ITERATIONS = MIN_ITERATIONS + 10000;
    
    long long m_totalIterations = 0;
    std::mutex m_totalItersLock;
    
    int getNumber()
    {
    
        std::uniform_int_distribution<int> num_distribution(MIN_ITERATIONS, MAX_ITERATIONS);
        std::mt19937 random_number_engine; // pseudorandom number generator
        auto get_num = std::bind(num_distribution, random_number_engine);
        int random_num = get_num();
    
        auto result = 0;
        {
            std::lock_guard<std::mutex> lock(m_totalItersLock);
            m_totalIterations += random_num;
        }
        // we're just spinning here  
        // to increase CPU usage 
        for (int i = 0; i < random_num; i++)
        {
            result = get_num();
        }
        return result;
    }
    
    void doWork()
    {
        std::wcout << L"The doWork function is running on another thread." << std::endl;
    
        auto x = getNumber();    
    }
    
    int main()
    {
        std::vector<std::thread> threads;
    
        for (int i = 0; i < 10; ++i) {
    
            threads.push_back(std::thread(doWork));
            std::cout << "The Main() thread calls this after starting the new thread" << std::endl;
        }
    
        for (auto& thread : threads) {
            thread.join();
        }
    
        return 0;
    }
    ```
  
## <a name="step-1-collect-profiling-data"></a>Krok 1: Shromáždění data profilování 
  
1.  Nejdřív nastavit zarážky ve vaší aplikaci tento řádek kódu `main` funkce:

    `for (int i = 0; i < 10; ++i) {`

    Nastavte zarážky kliknutím v mřížky doleva řádek kódu.

2.  V dalším kroku nastavení druhý zarážky na pravé složené závorce na konci `main` funkce:

     ![Nastavte zarážky pro profilace](../profiling/media/quickstart-cpu-usage-breakpoints-cplusplus.png "nastavit zarážky pro profilaci")

    > [!TIP]
    > Nastavením dvou zarážek omezíte shromažďování dat jenom na analyzovanou část kódu.
  
3.  **Diagnostické nástroje** okno již viditelné, pokud jste vypnuli ho. Zobrazte okno znovu, klikněte na tlačítko **ladění**>**Windows**>**zobrazit diagnostické nástroje**.

4.  Klikněte na tlačítko **ladění**>**spustit ladění** (nebo **spustit** na panelu nástrojů nebo **F5**).

     Po dokončení načítání, aplikace **Souhrn** diagnostické nástroje se zobrazí.

5.  Při ladicího programu je pozastavena, povolení shromažďování těchto dat o využití procesoru výběrem **záznam procesoru profil**a pak otevřete **využití procesoru** kartě.

     ![Diagnostické nástroje povolit profilace procesoru](../profiling/media/quickstart-cpu-usage-summary.png "diagnostické nástroje povolit procesoru profilace")

     Pokud je povoleno shromažďování dat, zobrazí tlačítko záznam červeném kroužku.

     Pokud vyberete **záznam procesoru profil**, Visual Studio bude nahráváním funkcí a jak dlouho budou chtít provést a také poskytuje časová osa grafu, můžete se zaměřit na konkrétní segmenty relace vzorkování. Tato shromážděná data můžete zobrazit, jenom když aplikace se zastavilo na zarážce.

6.  Stiskněte klávesu F5, kterou spustíte aplikaci až ke druhé zarážce.

     Teď máte údaje o výkonu aplikace přesně pro oblast kódu spuštěnou mezi dvěma zarážkami.

     Profiler začne připravovat údaje o vlákně. Počkejte, až skončí.
  
     V nástroji Využití procesoru se na kartě **Využití procesoru** zobrazí sestava.

     Teď můžete začít analyzovat data.

## <a name="step-2-analyze-cpu-usage-data"></a>Krok 2: Analyzovat data o využití procesoru

Analýzu dat doporučujeme začít tím, že zkontrolujete seznam funkcí na kartě Využití procesoru. Zjistěte nejaktivnější funkce a pak se na každou z nich podívejte podrobněji.

1. V seznamu funkcí se podívejte, jaké funkce vykonávají většinu práce.

     ![Karta Využití procesoru v diagnostických nástrojích](../profiling/media/quickstart-cpu-usage-cpu-cplusplus.png "DiagToolsCPUUsageTab")

    > [!TIP]
    > Funkce jsou seřazené od nejvíce pracujících po nejméně pracující (nejsou seřazené podle pořadí, v jakém byly volány). Pomůže vám to rychle identifikovat funkce, které běží nejdéle.

2. V seznamu funkce dvakrát klikněte `getNumber` funkce.

    Když dvakrát kliknete funkce **volající/volaný** zobrazení se otevře v levém podokně. 

    ![Zobrazení Volající/volaný v diagnostických nástrojích](../profiling/media/quickstart-cpu-usage-caller-callee-cplusplus.png "DiagToolsCallerCallee")

    V tomto zobrazení vybrané funkce se zobrazí v záhlaví a v **aktuální funkce** pole (`getNumber`, v tomto příkladu). Funkce, která volala aktuální funkci, se zobrazí vlevo v části **Volající funkce** a všechny funkce volané aktuální funkcí se zobrazí vpravo v poli **Volané funkce**. (Pokud chcete aktuální funkci změnit, vyberte libovolné pole.)

    V tomto zobrazení vidíte celkový čas (ms) a procento z celkové doby spuštění aplikace, kterou funkce potřebovala k dokončení.

    **Tělo funkce** také zobrazuje celkovou dobu (a procento času) spotřebovanou tělem funkce, ale bez doby spotřebované volajícími a volanými funkcemi. (V tomto obrázku 119 mimo 43602 ms byly věnovaný tělo funkce a zbývající doba strávená v jiném kódu volat pomocí této funkce). Skutečné hodnoty bude velmi lišit v závislosti na vašem prostředí.

    > [!TIP]
    > Vysoké hodnoty v **těle funkce** pravděpodobně znamenají kritické místo výkonu samotné funkce.

## <a name="next-steps"></a>Další kroky

- [Analýza využití paměti](../profiling/memory-usage.md)identifikovat kritická místa výkonu.
- [Analýza využití procesoru](../profiling/cpu-usage.md) podrobnější informace o nástroji využití procesoru.
- Analýza využití procesoru bez připojit ladicí program nebo cílením spuštěné aplikaci - Další informace najdete v tématu [shromažďování dat profilaci bez ladění](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) v [spustit profilování nástroje s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Viz také:  

 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md)
