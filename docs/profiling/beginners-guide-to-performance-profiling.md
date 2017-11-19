---
title: "Příručka začátečníka profilací výkonu v sadě Visual Studio | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords: vs.performance.wizard.intropage
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
- CPU Usage
- Diagnostics Tools
ms.assetid: da2fbf8a-2d41-4654-a509-dd238532d25a
caps.latest.revision: "45"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b907be5e46b6d8d33232d120d4229b0e205f948b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="beginners-guide-to-performance-profiling"></a>Příručka začátečníka profilací výkonu
Nástroje pro profilaci sady Visual Studio můžete použít k analýze problémy s výkonem v aplikaci. Tento postup ukazuje, jak používat **využití procesoru** kartě diagnostické nástroje získat údaje o výkonu pro vaši aplikaci. Diagnostické nástroje jsou podporované pro .NET – vývoj v sadě Visual Studio, včetně ASP.NET a pro vývoj nativní/C++.
  
Když ladicí program pozastaví, **využití procesoru** nástroj shromažďuje informace o funkcích, které jsou prováděny ve vaší aplikaci. Nástroj obsahuje seznam funkcí, které byly provede práci a poskytuje časová osa grafu, které můžete používat a zaměřit se na konkrétní segmenty relace vzorkování.

Centrum diagnostiky nabízí mnoho dalších možností spouštět a spravovat relace diagnostiky. Pokud **využití procesoru** nezískáte data, která budete potřebovat, [jiných nástrojů pro profilaci](../profiling/Profiling-Tools.md) poskytují různé druhy informace, které mohou být užitečné pro vás. V mnoha případech kritická místa výkonu aplikace může být způsobeno něco jiného než procesoru, jako je například paměť, vykreslování uživatelského rozhraní nebo doba požadavku sítě. Centrum diagnostiky nabízí spoustu dalších možností zaznamenávat a analyzovat tento druh data.

|         |         |
|---------|---------|
| ![Přehrát video,](../install/media/video-icon.png "WatchVideo") | [Přehrát video,](#video) o používání nástroje diagnostiky, které ukazuje, jak analyzovat využití procesoru a jak pro analýzu využití paměti. |

V tomto tématu probereme analýza využití procesoru v normálním pracovním postupu ladění. Můžete také analyzovat využití procesoru bez připojit ladicí program nebo cílením spuštěné aplikaci - Další informace najdete v tématu [shromažďování dat profilaci bez ladění](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) v [spuštění profilace nástroje s nebo bez něj](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a>Krok 1: Shromáždění data profilování 
  
1.  Otevřete projekt, který chcete ladit v sadě Visual Studio a nastavit zarážky ve vaší aplikaci v okamžiku, kdy chcete prověřit využití procesoru.

2.  Druhý zarážku na konci funkce nebo kód, který chcete analyzovat oblasti.

    > [!TIP]
    > Nastavením dvě zarážky můžete omezit shromažďování dat na části kódu, který chcete analyzovat.
  
3.  **Diagnostické nástroje** okno se automaticky zobrazí, pokud jste vypnuli ho. Zobrazte okno znovu, klikněte na tlačítko **ladění / Windows / zobrazit diagnostické nástroje**.

4.  Můžete vybrat, jestli chcete zobrazit **využití procesoru**, [využití paměti](../profiling/Memory-Usage.md), nebo obojí, s **vyberte nástroje** nastavení na panelu nástrojů. Pokud používáte Visual Studio Enterprise, můžete také povolit nebo zakázat IntelliTrace v **nástroje / Možnosti / IntelliTrace**.

     ![Zobrazit nástroje pro diagnostiku](../profiling/media/DiagToolsSelectTool.png "DiagToolsSelectTool")

     Jsme budou především prohlížení využití procesoru, tak zkontrolujte, zda **využití procesoru** je povoleno (je povolená ve výchozím nastavení).

5.  Klikněte na tlačítko **ladění / spusťte ladění** (nebo **spustit** na panelu nástrojů nebo **F5**).

     Po dokončení nahrávání aplikace se zobrazí přehled o diagnostické nástroje.

     ![Diagnostické nástroje kartu Souhrn](../profiling/media/DiagToolsSummaryTab.png "DiagToolsSummaryTab")

     Další informace o události najdete v tématu [hledání a filtrování kartě události v okně diagnostické nástroje](http://blogs.msdn.com/b/visualstudioalm/archive/2015/11/12/searching-and-filtering-the-events-tab-of-the-diagnostic-tools-window.aspx)

6.  Spusťte scénář, který způsobí, že vaše první zarážky být narazí.

7.  Během ladicí program je pozastavena, povolení shromažďování těchto dat o využití procesoru a pak otevřete **využití procesoru** kartě.

     ![Diagnostické nástroje povolit profilace procesoru](../profiling/media/DiagToolsEnableCPUProfiling.png "DiagToolsEnableCPUProfiling")

     Pokud vyberete **povolit profilace procesoru**, Visual Studio bude nahráváním funkcí a jak dlouho budou chtít provést. Tato shromážděná data můžete zobrazit, jenom když aplikace se zastavilo na zarážce.

8.  Stiskněte F5 a spusťte aplikaci k vaší zarážce druhý.

     Nyní nyní máte údaje o výkonu pro vaši aplikaci speciálně pro oblast kód, který běží mezi dvěma zarážky.

9.  Vyberte oblast, co vás zajímá analýza v časové ose procesoru (musí to být oblasti, která zobrazuje profilace data).

     ![Diagnostické nástroje Výběr Segment čas](../profiling/media/DiagToolsSelectTimeSegment.png "DiagToolsSelectTimeSegment")

     Profileru začne přípravu dat přístup z více vláken. Počkejte na její dokončení.

     ![Diagnostické nástroje Příprava vláken](../profiling/media/DiagToolsPreparingThreads.png "DiagToolsPreparingThreads")
  
     Zobrazí sestavu v nástroj využití procesoru **využití procesoru** kartě.
  
     ![Diagnostické nástroje využití CPU karta](../profiling/media/DiagToolsCPUUsageTab.png "DiagToolsCPUUsageTab")

     V tomto okamžiku můžete začít analyzovat data.

## <a name="Step2"></a>Krok 2: Analyzovat data o využití procesoru

Doporučujeme začít analýza dat kontrolou seznamu funkcí podle využití procesoru, určení funkcí, které pracujeme na maximum a pak trvá bližší pohled na každé z nich.

1. V seznamu funkce zkontrolujte funkce, které pracujeme na maximum.

    ![Diagnostické nástroje využití CPU funkce seznamu](../profiling/media/DiagToolsCPUUsageFunctionList.png "DiagToolsCPUUsageFunctionList")

    > [!TIP]
    > Funkce jsou uvedeny v pořadí od těch, které nejvíce pracuje (nejsou v pořadí volání). Díky tomu můžete rychle zjistit nejdelší spuštěné funkce.

2. V seznamu funkce dvakrát klikněte na jednu z vaší aplikace funkce, které provádí spoustu práce.

    Když dvakrát kliknete funkce **volající/volaný** zobrazení se otevře v levém podokně. 

    ![Diagnostické nástroje volající volaný – zobrazení](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")

    V tomto zobrazení vybrané funkce se zobrazí v záhlaví a v **funkci Current** pole (v tomto příkladu GetNumber). Funkce, která volá funkci current se zobrazí na levé straně v části **volání funkce**, a všechny funkce volá funkci current se zobrazují v **volat funkce** pole na pravé straně. (Můžete vybrat buď použijte ke změně aktuální funkce.)

    Toto zobrazení uvádí celkový čas (ms) a procento celkového aplikaci spuštěnou dobu, po kterou funkce provedlo v návaznosti na Dokončit.

    **Funkce text** také ukazuje celkové množství času (a procentuální hodnotu času) věnovaný tělo funkce bez doby věnovaný volání a funkce s názvem. (V tomto příkladu. 3713 mimo 3729 ms byly věnovaný tělo funkce a zbývajících 16 ms byly věnovaný externí kódu volaného pomocí této funkce).

    > [!TIP]
    > Vysoce hodnoty v **tělo funkce** může znamenat přetížení v rámci funkce sám sebe.

3. Pokud chcete zobrazit vyšší úrovně pořadí, ve kterém jsou funkce názvem, vyberte zobrazení **volání stromu** z rozevíracího seznamu v horní části podokna.
 
    Každou číslem oblast na obrázku má vztah k krok v postupu.
  
    ![Diagnostické nástroje volání stromu](../profiling/media/DiagToolsCallTree.png "DiagToolsCallTree")
  
|||
|-|-|
|![Krok 1](../profiling/media/ProcGuid_1.png "ProcGuid_1")|Uzel na nejvyšší úrovni ve stromech volání využití procesoru je pseudo uzel|  
|![Krok 2](../profiling/media/ProcGuid_2.png "ProcGuid_2")|Ve většině aplikací když [zobrazit externí kód](#BKMK_External_Code) možnost je vypnuta, je uzel druhé úrovně **[externí kód]** uzlu, který obsahuje systém a architektura kód, který spustí a ukončí aplikaci a nevykresluje uživatelského rozhraní, ovládací prvky plánování vláken a poskytuje jiných nízké úrovně služeb k aplikaci.|  
|![Krok 3](../profiling/media/ProcGuid_3.png "ProcGuid_3")|Podřízené objekty daného uzlu druhé úrovně jsou metody uživatelského kódu a asynchronní rutiny, které jsou volány, nebo vytvořené druhé úrovně systému a framework kódu.|
|![Krok 4](../profiling/media/ProcGuid_4.png "ProcGuid_4")|Podřízené uzly metody obsahovat data jen pro volání metody nadřazené. Když **zobrazit externí kód** je zakázaná, metody aplikace může také obsahovat **[externí kód]** uzlu.|

Zde je další informace o hodnoty ve sloupcích:

- **Celkový počet procesoru** Určuje, kolik práce se provádí funkce a všechny funkce je volána. Vysoká celkové hodnoty využití procesoru, přejděte na funkce, které jsou nejnákladnější celkové.
  
- **Vlastní procesoru** Určuje, kolik práce bylo provedeno pomocí kódu v tělo funkce, s výjimkou podle funkce, které byly volány. Vysoká **samoobslužné procesoru** hodnoty může znamenat přetížení v rámci funkce sám sebe.

- **Moduly** název modul, který obsahuje funkce, nebo počet modulů obsahující funkce v uzlu služby [externí kód].

## <a name="BKMK_External_Code"></a>Zobrazení externí kódu

Externí kódu jsou funkcí v systému a framework komponenty, provedený kód napíšete. Externí kód zahrnují funkce, které spuštění a zastavení aplikace, vykreslení uživatelského rozhraní, řídit vlákna a poskytují jiných nízké úrovně služeb k aplikaci. Ve většině případů nebude zájem o externí kód, a proto nástroj využití procesoru shromažďuje externí funkce metody uživatele do jedné **[externí kód]** uzlu.
  
Pokud chcete zobrazit cesty volání externí kódu, zvolte **zobrazit externí kód** z **filtrovat zobrazení** seznamu a potom zvolte **použít**.  
  
![Zvolte zobrazení filtru, a zobrazit externí kód](../profiling/media/DiagToolsShowExternalCode.png "DiagToolsShowExternalCode")  
  
Mějte na paměti, že jsou vnořeny hluboko mnoho řetězy volání externí kód, tak, aby šířka sloupce název funkce může být vyšší než šířka zobrazení všech ale největší monitorování počítače. V takovém případě se zobrazují názvy funkcí jako **[...]** .
  
Použijte pole hledání najít uzel, který hledáte, potom použijte vodorovného posuvníku přenést data do zobrazení.

> [!TIP]
> Pokud je profil externí kód, který volá funkce systému Windows, měli byste si ověřit, že máte nejnovější soubory PDB. Bez těchto souborů v zobrazeních sestav zobrazí seznam názvů funkce Windows, které jsou jako nesrozumitelné a vzhledem k. Další informace o tom, abyste měli jistotu, že máte soubory, které potřebujete, najdete v části [zadejte symbolu (.pdb) a zdrojových souborů v ladicím programu](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).

## <a name="video"></a>Podívejte se na video o používání diagnostické nástroje

<div style="padding-top: 56.25%; position: relative; width: 100%;">
<iframe style="position: absolute;top: 0;left: 0;right: 0;bottom: 0;" width="100%" height="100%" src="https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171" frameborder="0" allowfullscreen></iframe>
</div>
  
## <a name="see-also"></a>Viz také  
 [[Využití paměti](../profiling/memory-usage.md)  
 [Využití procesoru](../profiling/cpu-usage.md)  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)
