---
title: Analýza spotřeby prostředků ve aplikace XAML v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: df7d854b-0a28-45a9-8a64-c015a4327701
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 8d5eca01cc5a9f910c16685f4aec36cd69f37a94
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
---
# <a name="analyze-resource-consumption-and-ui-thread-activity-xaml"></a>Analýza spotřeby prostředků a aktivita vláken uživatelského rozhraní (XAML)
Použití **časová osa aplikace** profileru najít a opravit interakce aplikace související s problémy s výkonem v aplikacích XAML. Tento nástroj pomáhá zlepšit výkon aplikace XAML tím, že poskytuje podrobný přehled o spotřeby prostředků aplikace. Čas strávený aplikací Příprava rámce uživatelského rozhraní (rozložení a vykreslování), sítě a disku požadavky obsluhy a ve scénářích, jako je spuštění aplikace, načítání stránky, můžete analyzovat a změňte velikost systému Windows.  
  
 **Časová osa aplikace** je jedním z nástrojů můžete začít s **ladění** > **výkonu profileru** příkaz.  
  
 Tento nástroj nahradí **odezvy uživatelského rozhraní jazyka XAML** nástroj, který byl součástí diagnostických nástrojů pro Visual Studio 2013.  
  
 Tento nástroj můžete použít na následujících platformách:  
  
1.  Univerzální aplikace pro Windows (ve Windows 10)  
  
2.  Windows 8.1  
  
4.  Windows Presentation Foundation (rozhraní .net 4.0 a novější)  
  
5.  Windows 7  
  
> [!NOTE]
>  Můžete shromažďovat a analyzovat data o využití procesoru a datům o spotřebě energie spolu s **ApplicationTimeline** data. V tématu [spuštění nástroje pro profilaci s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
## <a name="collect-application-timeline-data"></a>Shromažďování dat časová osa aplikace  
 Profil rychlost reakce aplikace na místním počítači, připojeného zařízení, Visual Studio simulátoru nebo emulátorů nebo vzdáleném zařízení V tématu [spuštění nástroje pro profilaci s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
> [!TIP]
>  Pokud je to možné spusťte aplikaci přímo v zařízení. Výkon aplikace dodržet v simulátoru, nebo prostřednictvím připojení ke vzdálené ploše nemusí být stejný jako skutečný výkon v zařízení. Na druhé straně shromažďování dat pomocí nástrojů pro vzdálenou Visual Studio nemá vliv data výkonu.  
  
 Zde jsou základní kroky:  
  
1.  Otevřete aplikaci XAML.  
  
2.  Klikněte na tlačítko **ladění nebo výkonu profileru**. Zobrazí seznam profilace nástroje v okně .diagsession.  
  
3.  Vyberte **časová osa aplikace** a pak klikněte na **spustit** v dolní části okna.  
  
    > [!NOTE]
    >  Může se zobrazit okno Řízení uživatelských účtů vyžaduje vaše oprávnění ke spuštění VsEtwCollector.exe. Klikněte na tlačítko **Ano**.  
  
4.  Spusťte tento scénář vás zajímá profilace ve vaší aplikaci ke shromažďování dat výkonu.  
  
5.  Chcete-li zastavit profilování, přepněte zpět do okna .diagsession a klikněte na **Zastavit** v horní části okna.  
  
     Aplikace Visual Studio analyzuje shromážděná data a zobrazuje výsledky.  
  
     ![Časová osa sestav profileru](../profiling/media/timeline_base.png "TIMELINE_Base")  
  
## <a name="analyze-timeline-profiling-data"></a>Analýza dat profilaci časové osy  
 Chcete-li spustit analýzu, řiďte se po shromáždění profilačních dat těmito kroky:  
  
1.  Zkontrolujte informace v **využití vlákna uživatelského rozhraní** a **Visual propustnost (FPS)** grafech a pak vyberte časový rozsah, který chcete analyzovat pomocí časová osa navigační panely.  
  
2.  Podle informací uvedených v **využití vlákna uživatelského rozhraní** nebo **Visual propustnost (FPS)** grafy, zkontrolujte podrobnosti v **časová osa podrobnosti** zobrazení zjistit možné příčiny pro všechny zřejmá chybí odezvy.  
  
###  <a name="BKMK_Report_scenarios_categories_and_events"></a> Sestava scénáře, kategorie a události  
 **Časová osa aplikace** nástroj zobrazí dat časování pro scénáře, kategorie a události, které se vztahují k výkonu XAML.  
  
###  <a name="BKMK_Diagnostic_session_timeline"></a> Časová osa relace diagnostiky  
 ![Časová osa výkonu a Diagnostika](../profiling/media/diaghub_timelinewithusermarks.png "DIAGHUB_TimelineWithUserMarks")  
  
 Pravítka v horní části stránky zobrazí časovou osu pro PROFILOVANÉHO informace. Tuto časovou osu se vztahuje **využití vlákna uživatelského rozhraní** grafu a **Visual propustnost** grafu. Přetažením navigačních panelů na časové ose můžete vybrat určitou část časové osy a zúžit tak rozsah sestavy.  
  
 Na časové ose se také zobrazují všechny uživatelské značky, které jste tam vložili, a události z aktivačního životního cyklu aplikace.  
  
###  <a name="BKMK_UI_thread_utilization_graph"></a> Graf využití vlákna uživatelského rozhraní  
 ![Graf využití procesoru](../profiling/media/timeline_cpuutilization.png "TIMELINE_CpuUtilization")  
  
 **Využití vlákna uživatelského rozhraní (%)** grafu je pruhový graf, který zobrazí relativní množství času strávené v kategorii pro během kolekce rozpětí.  
  
###  <a name="BKMK_Visual_throughput_FPS_graph"></a> Diagram Visual propustnosti (FPS)  
 ![Diagram Visual propustnosti](../profiling/media/timeline_visualthroughput.png "TIMELINE_VisualThroughput")  
  
 **Visual propustnost (FPS)** spojnicový graf znázorňuje počet snímků za sekundu (FPS) ve vláknu uživatelského rozhraní a sestavení pro aplikaci.  
  
###  <a name="BKMK_Timeline_details_"></a> Podrobnosti časové osy  
 Zobrazení podrobností je, kde bude výdaje většinu doby analýza sestavy. Zobrazuje podrobný přehled o využití procesoru aplikace zařazený do kategorie službou subsystém uživatelského rozhraní Framework nebo součást systému, která využívá procesoru.  
  
 Podporovány jsou následující události:  
  
|||  
|-|-|  
|**Analýza**|Čas strávený analýzy soubory XAML a vytváření objektů.<br /><br /> Rozšiřování **Parsing** uzlu v **časová osa podrobnosti** zobrazí řetězec závislostí všechny soubory XAML, které byly analyzovat v důsledku události kořenové. To vám umožní identifikovat nepotřebných souborů analýzy a objekt vytvoření ve scénářích citlivé výkonu a optimalizovat je.|  
|**Rozložení**|V velké aplikace může být uvedené na obrazovce tisíce elementy ve stejnou dobu. To může způsobit nízkou obnovovací frekvence uživatelského rozhraní a odezvu odpovídajícím způsobem nízký aplikací. Událost rozložení přesně určuje náklady rozložení jednotlivých prvků (tj. čas věnovaný uspořádat, míry, ApplyTemplate, ArrangeOverride a ArrangeOverride) a vytvoří visual stromy, které trvalo část při průchodu rozložení. Tuto vizualizaci můžete použít k určení, které vaše logické stromy, chcete-li vyřadit nebo vyhodnotit jiným mechanismem odložení za účelem optimalizace vaší průchodu rozložení.|  
|**Vykreslení**|Čas strávený vykreslení elementů XAML na obrazovku.|  
|**I / 0**|Čas strávený načítání dat z místního disku nebo síťovým prostředkům, které jsou přístupné prostřednictvím [Microsoft Windows Internet (WinINet) rozhraní API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa385331.aspx).|  
|**Kód aplikace**|Čas strávený provádění kódu aplikace (uživatel), která nesouvisí se analýza nebo rozložení.|  
|**Další XAML**|Čas strávený provádění kódu runtime jazyka XAML.|  
  
> [!TIP]
>  Vyberte **využití procesoru** nástroj spolu s **časová osa aplikace** nástroj po spuštění profilace pro zobrazení aplikace metody, které jsou spouštěny ve vlákně UI. Přesunutí kód aplikace dlouho běžící vlákna na pozadí může zvýšit rychlost odezvy UI.  
  
####  <a name="BKMK_Customizing_Timeline_details_"></a> Přizpůsobení podrobnosti časové osy  
 Použití **podrobnosti časové osy** nástrojů řazení a filtrování, zadejte poznámky z **podrobnosti časové osy** zobrazení položky.  
  
|||  
|-|-|  
|**Řadit podle**|Řazení podle počáteční čas nebo délka události.|  
|![Seskupení událostí podle rámce](../profiling/media/timeline_groupbyframes.png "TIMELINE_GroupByFrames")|Přidá nebo odebere nejvyšší úrovně **rámce** kategorie, které jsou seskupeny události po rámce.|  
|![Seznam filtrů časová osa podrobnosti](../profiling/media/timeline_filter.png "TIMELINE_Filter")|Filtruje seznam podle vybraných kategorií a délka události.|  
|![Upravit podrobnosti informací časová osa](../profiling/media/timeline_viewsettings.png "TIMELINE_ViewSettings")|Umožňuje zadat poznámky k událostem.|  
  
## <a name="see-also"></a>Viz také  
 [Blog týmu WPF: nástroj pro analýzu výkonu nové uživatelské rozhraní pro aplikace WPF](http://blogs.msdn.com/b/wpf/archive/2015/01/16/new-ui-performance-analysis-tool-for-wpf-applications.aspx)  
 [Osvědčené postupy z hlediska výkonu pro aplikace UWP pomocí C++, C# a Visual Basic](http://msdn.microsoft.com/en-us/567bcefa-5da5-4e42-a4b8-1358c71adfa2)   
 [Optimalizace výkonu aplikace WPF](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md)
