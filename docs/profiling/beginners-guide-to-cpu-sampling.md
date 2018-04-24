---
title: Průvodce začátečníka vzorkování procesoru v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 02/27/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.wizard.intropage
helpviewer_keywords:
- Profiling Tools, quick start
- performance tools, wizard
- Performance Wizard
ms.assetid: 85161cc4-18ee-49b3-9487-33680e687597
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee85f9946e16b0ecaafa196e1b197304ccde3bd9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="beginners-guide-to-cpu-sampling"></a>Průvodce začátečníka procesoru vzorkování
Nástroje pro profilaci sady Visual Studio můžete použít k analýze problémy s výkonem v aplikaci. Tento postup ukazuje, jak používat **vzorkování** data.

> [!NOTE]
>  Doporučujeme použít [využití procesoru](../profiling/beginners-guide-to-performance-profiling.md) nástroje v okně diagnostické nástroje místo starší verze nástroje procesoru vzorkování, pokud budete potřebovat speciální funkce jako je podpora instrumentace.
  
 **Vzorkování** je statistické profilování metoda, která ukazuje, pracovní funkce, které provádějí většinu režimu uživatele v aplikaci. Vzorkování je vhodná k zjištění oblastí zrychlit aplikace.  
  
 V určitých intervalech **vzorkování** metoda shromažďuje informace o funkcích, které jsou prováděny ve vaší aplikaci. Po dokončení profilace spustit, **Souhrn** zobrazení profilace data zobrazují stromu Nejaktivnější volání funkce volá **aktivní trase**, kde byla provedena většinu práce v aplikaci. Zobrazení také uvádí funkce, které byly provádění většiny jednotlivých pracovních a nabízí časová osa grafu, které můžete používat a zaměřit se na konkrétní segmenty relace vzorkování.  
  
 Pokud **vzorkování** nezískáte data, která budete potřebovat, ostatní profilování kolekce metody nástroje poskytují různé druhy informace, které mohou být užitečné pro vás. Další informace o těchto dalších metod najdete v tématu [postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md).  
  
> [!TIP]
>  Pokud kód, který volá funkce systému Windows, profilu, měli byste si ověřit, že máte nejnovější soubory PDB. Bez těchto souborů v zobrazeních sestav zobrazí seznam názvů funkce Windows, které jsou jako nesrozumitelné a vzhledem k. Další informace o tom, abyste měli jistotu, že máte soubory, které potřebujete, najdete v části [postupy: odkaz na informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md).  
  
##  <a name="Step1"></a> Vytvoření a spuštění výkonnostní relace  
 Pokud chcete získat data, která potřebujete analyzovat, musíte nejprve vytvořit relaci výkonu a spusťte relaci. **Průvodce výkonu** umožňuje proveďte obojí.  
  
 Pokud nejsou profilace aplikace na ploše systému Windows nebo aplikace ASP.NET, musí používat jednu z dalších nástrojů pro profilaci. V tématu [nástroje pro profilaci](../profiling/profiling-tools.md).  
  
#### <a name="to-create-and-run-a-performance-session"></a>Vytvořit a spustit výkonnostní relace  
  
1.  Otevřete řešení v sadě Visual Studio. Nastavte konfiguraci na verzi. (Najít **konfigurace řešení** na panelu nástrojů, který je nastaven na **ladění** ve výchozím nastavení. Změňte ho na **verze**.)  
  
    > [!IMPORTANT]
    >  Pokud si nejste správce v počítači, který používáte, byste měli při používání profileru spustit Visual Studio jako správce. (Klikněte pravým tlačítkem myši na ikonu aplikace Visual Studio a pak klikněte na **spustit jako správce**.  
  
2.  Na **ladění** nabídce vyberte možnost **profileru**a potom vyberte **výkonu profileru**.  
  
3.  Zkontrolujte **Průvodce výkonu** a klikněte na **spustit**.  
  
4.  Zkontrolujte **vzorkování procesoru (doporučeno)** možnost a klikněte na tlačítko **Dokončit**.  
  
5.  Spuštění aplikace a profileru začne shromažďovat data.  
  
6.  Výkonu funkce, které mohou obsahovat problémy s výkonem.  
  
7.  Zavře se aplikace, stejně jako obvykle.  
  
     Po spuštění aplikace, **Souhrn** v hlavním okně Visual Studio se zobrazí zobrazení data profilování a ikonu pro novou relaci v **prohlížeč výkonu** okno.  
  
##  <a name="Step2"></a> Krok 2: Analýza dat vzorkování  
 Po dokončení spuštění výkonnostní relace **Souhrn** profilování sestavy se zobrazí v hlavním okně v sadě Visual Studio.  
  
 Doporučujeme začít analýza dat tak, že prověří **aktivní trase,** pak seznam funkcí, které jsou nejvíce pracuje a nakonec pomocí zaměřené na jiných funkcí s použitím **časová osa Souhrn** . Můžete také zobrazit profilování návrhy a upozornění v **seznam chyb** okno.  
  
 Upozorňujeme, že metoda vzorkování nemusí získáte informace, které potřebujete. Například ukázky se shromažďují jenom v případě, že aplikace je provádění kódu v režimu uživatele. Některé funkce, jako jsou vstupní a výstupní operace, není proto zachycenou vzorkování. Nástroje pro profilaci poskytují několik metod kolekce, které vám umožní zaměřit se na důležitá data, můžete povolit. Další informace o dalších metodách v tématu [postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md).  
  
 Každou číslem oblast na obrázku má vztah k krok v postupu.  
  
 ![Zobrazení souhrnné sestavy pro vzorkování](../profiling/media/summary_sampling.png "Summary_Sampling")  
  
#### <a name="to-analyze-sampling-data"></a>K analýze dat vzorkování  
  
1.  V **Souhrn** zobrazení, **aktivní trase** ukazuje větev stromu volání aplikace s nejvyšší ukázky (včetně). Je to cesta ke spuštění, který byl nejvíce aktivní, pokud data nebyla shromážděna. Vysoká (včetně). hodnoty můžou značit, že algoritmus, který generuje stromu volání lze optimalizovat. Najít funkce ve vašem kódu, který je nejnižší v cestě. Všimněte si, že cesta může také obsahovat funkce systému nebo funkce v modulech externí.  
  
     ![Profiler Hot Path](../profiling/media/profiler_hotpath.png "Profiler_HotPath")  
  
    1.  **Včetně ukázky** určit, kolik práce se provádí funkce a všechny funkce je volána. Vysoké počty (včetně). přejděte na funkce, které jsou nejnákladnější celkové.  
  
    2.  **Výhradní ukázky** určit, kolik práce bylo provedeno pomocí kódu v tělo funkce, s výjimkou podle funkce, které byly volány. Vysoké počty výhradní může znamenat přetížení v rámci funkce sám sebe.  
  
2.  Klikněte na název funkce zobrazíte **podrobností funkce** zobrazení data profilování. **Podrobností funkce** zobrazení poskytuje grafické zobrazení profilace data pro vybrané funkce, všechny funkce, které volá této funkce a všechny funkce, které byly volány vybrané funkce.  
  
    -   Velikost bloků volající a volaná funkce představují relativní frekvenci funkce volá nebo byla volána.  
  
    -   Kliknutím na název volání nebo volal funkci chcete-li funkci vybrané zobrazení podrobností funkce.  
  
    -   Ve spodní části podokna **podrobností funkce** systém windows zobrazí samotný kód funkce. Pokud kód zkontrolovat a najít příležitost k optimalizaci jeho výkon, klikněte na název zdrojového souboru k otevření souboru v editoru Visual Studio.  
  
3.  Chcete-li pokračovat analýzy, vraťte se k **Souhrn** zobrazení tak, že vyberete **Souhrn** z rozevíracího seznamu zobrazení. Potom si prohlédněte funkcí v **nejvíce jednotlivých pracuje funkce**. Tento seznam obsahuje funkce s nejvyšší výhradní ukázky. Kód v těle funkce těchto funkcí provést velice pracné je možné ji optimalizovat. K další analýze určitou funkci, klikněte na název funkce zobrazte jej v **podrobností funkce** zobrazení.  
  
     ![Seznam funkcí, které nejvíce pracuje](../profiling/media/functions_mostwork.png "Functions_MostWork")  
  
     Pokračujte šetření z profilace spustit je můžete opakovat analýzu segment data profilování pomocí časové osy v **Souhrn** zobrazení tak, aby zobrazovalo **aktivní trase** a **funkce Většina jednotlivých pracuje** z vybraného segmentu. Například zaměřené na menší ve špičce v časové ose může odhalit nákladné volání stromy a funkce, které nejsou uvedené v analýzu celého profilace spustit.  
  
     Pokud chcete opakovat analýzu segment, vyberte segment uvnitř pole Časová osa souhrn a pak klikněte na tlačítko **filtrovat podle výběru**.  
  
     ![Časová osa zobrazení se souhrnnými informacemi výkonu](../profiling/media/performancesummary.png "PerformanceSummary")  
  
4.  Profileru také používá sada pravidel, zjistíte, jak zlepšit profilování spustit a identifikovat problémy s výkonem možné. Pokud je nalezen problém, zobrazí se upozornění v **seznam chyb** okno. Chcete-li otevřít **seznam chyb** okno na **zobrazení** nabídce klikněte na tlačítko **seznam chyb**.  
  
    -   Chcete-li zobrazit funkce, která vyvolá upozornění **podrobností funkce** klikněte dvakrát na upozornění.  
  
    -   Chcete-li zobrazit podrobné informace o upozornění, klikněte pravým tlačítkem na chybu a pak klikněte na **zobrazit nápovědu k chybě**  
  
##  <a name="Step3"></a> Krok 3: Zkontrolovat kód a znovu spusťte relaci  
 Po najít a optimalizovat jednu nebo více funkcí, můžete opakovat profilování spustit a porovnávání dat rozdíl, která provedla změny na výkon vaší aplikace.  
  
#### <a name="to-revise-code-and-rerun-the-profiler"></a>Chcete-li zkontrolovat kód a znovu spusťte profileru  
  
1.  Upravit svůj kód.  
  
2.  Otevřete **prohlížeč výkonu**na **ladění** nabídce klikněte na tlačítko **profileru**, pak **prohlížeč výkonu** a pak klikněte na **Zobrazit prohlížeč výkonu**.  
  
3.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na relace, který chcete znovu spustit a pak klikněte na tlačítko **spouštění profilování.**  
  
4.  Po je znovu spustit relaci, je do jiného souboru dat **sestavy** složku pro relaci v **prohlížeč výkonu**. Vyberte obě původní a nové profilace data, klikněte pravým tlačítkem na výběr a pak klikněte na **porovnat sestavy pro zvýšení výkonu**.  
  
     Otevře se nové okno sestavy, zobrazení výsledků porovnání. Další informace o tom, jak použít zobrazení porovnání najdete v tématu [postupy: porovnávání datových souborů výkonu](../profiling/how-to-compare-performance-data-files.md).
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)   
 [Začínáme](../profiling/getting-started-with-performance-tools.md)   
 [Přehledy](../profiling/overviews-performance-tools.md)  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)