---
title: Analyzovat data o využití procesoru (C++) | Microsoft Docs
ms.custom: ''
ms.date: 12/05/2017
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: ebe10dbcf5b03288ae4d0e6d2fb93444abe1064a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-cpu-usage-data-in-visual-studio-c"></a>Analyzovat data o využití procesoru v aplikaci Visual Studio (C++)

Visual Studio poskytuje mnoho výkonné funkce, které vám pomůžou analyzovat problémy s výkonem v aplikaci. Toto téma poskytuje rychlý způsob, jak další některé základní funkce. Zde podíváme na nástroj, který identifikovat kritická místa výkonu z důvodu vysoké využití procesoru. Diagnostické nástroje jsou podporované pro .NET – vývoj v sadě Visual Studio, včetně ASP.NET a pro vývoj nativní/C++.

Centrum diagnostiky nabízí mnoho dalších možností spouštět a spravovat relace diagnostiky. Pokud **využití procesoru** nástroj zde popsané nezískáte data, která budete potřebovat, [jiných nástrojů pro profilaci](../profiling/profiling-feature-tour.md) poskytují různé druhy informace, které mohou být užitečné pro vás. V mnoha případech kritická místa výkonu aplikace může být způsobeno něco jiného než procesoru, jako je například paměť, vykreslování uživatelského rozhraní nebo doba požadavku sítě. Centrum diagnostiky nabízí spoustu dalších možností zaznamenávat a analyzovat tento druh data.

## <a name="create-a-project"></a>Vytvoření projektu

1. V sadě Visual Studio, vyberte **soubor > Nový projekt**.

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
  
##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a> Krok 1: Shromáždění data profilování 
  
1.  Nejdřív nastavit zarážky ve vaší aplikaci tento řádek kódu `main` funkce:

    `for (int i = 0; i < 10; ++i) {`

    Nastavte zarážky kliknutím v mřížky doleva řádek kódu.

2.  V dalším kroku nastavení druhý zarážky na pravé složené závorce na konci `main` funkce:

     ![Nastavte zarážky pro profilace](../profiling/media/quickstart-cpu-usage-breakpoints-cplusplus.png "nastavit zarážky pro profilaci")

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

## <a name="Step2"></a> Krok 2: Analyzovat data o využití procesoru

Doporučujeme začít analýza dat kontrolou seznamu funkcí podle využití procesoru, určení funkcí, které pracujeme na maximum a pak trvá bližší pohled na každé z nich.

1. V seznamu funkce zkontrolujte funkce, které pracujeme na maximum.

     ![Diagnostické nástroje využití CPU karta](../profiling/media/quickstart-cpu-usage-cpu-cplusplus.png "DiagToolsCPUUsageTab")

    > [!TIP]
    > Funkce jsou uvedeny v pořadí od těch, které nejvíce pracuje (nejsou v pořadí volání). Díky tomu můžete rychle zjistit nejdelší spuštěné funkce.

2. V seznamu funkce dvakrát klikněte `getNumber` funkce.

    Když dvakrát kliknete funkce **volající/volaný** zobrazení se otevře v levém podokně. 

    ![Diagnostické nástroje volající volaný – zobrazení](../profiling/media/quickstart-cpu-usage-caller-callee-cplusplus.png "DiagToolsCallerCallee")

    V tomto zobrazení vybrané funkce se zobrazí v záhlaví a v **aktuální funkce** pole (`getNumber`, v tomto příkladu). Funkce, která volá funkci current se zobrazí na levé straně v části **volání funkce**, a všechny funkce volá funkci current se zobrazují v **volat funkce** pole na pravé straně. (Můžete vybrat buď použijte ke změně aktuální funkce.)

    Toto zobrazení uvádí celkový čas (ms) a procento celkového aplikaci spuštěnou dobu, po kterou funkce provedlo v návaznosti na Dokončit.

    **Funkce text** také ukazuje celkové množství času (a procentuální hodnotu času) věnovaný tělo funkce bez doby věnovaný volání a funkce s názvem. (V tomto obrázku 119 mimo 43602 ms byly věnovaný tělo funkce a zbývající doba strávená v jiném kódu volat pomocí této funkce). Skutečné hodnoty bude velmi lišit v závislosti na vašem prostředí.

    > [!TIP]
    > Vysoce hodnoty v **tělo funkce** může znamenat přetížení v rámci funkce sám sebe.

## <a name="next-steps"></a>Další kroky

- [Analýza využití paměti](../profiling/memory-usage.md)identifikovat kritická místa výkonu.
- [Analýza využití procesoru](../profiling/cpu-usage.md) podrobnější informace o nástroji využití procesoru.
- Analýza využití procesoru bez připojit ladicí program nebo cílením spuštěné aplikaci - Další informace najdete v tématu [shromažďování dat profilaci bez ladění](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) v [spustit profilování nástroje s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Viz také  

 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md)
