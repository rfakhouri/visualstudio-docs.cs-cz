---
title: "Analýza využití procesoru v aplikaci pro univerzální Windows | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c122b08e-e3bf-43e6-bd6c-e776e178fd9a
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 59669f0430760bb98dd0cb63e05f433cb3a1fe54
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="analyze-cpu-usage-in-a-universal-windows-app-uwp"></a>Analýza využití procesoru v aplikaci univerzální pro Windows (UWP)
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Když potřebujete prozkoumat problémy s výkonem v aplikaci, je vhodné oddělení na zahájení pochopení, jak používá procesoru. **Využití procesoru** nástroj ukazuje, kde je procesoru výdaje provádění kódu v době. Umožňuje zaměřit se na konkrétní scénáře, mohou být spuštěny využití procesoru [časová osa aplikace](../profiling/application-timeline.md) nástroj [spotřeba energie na](../profiling/analyze-energy-use-in-store-apps.md) nástroje nebo oba nástroje v rámci jedné relace diagnostiky.  
  
> [!NOTE]
>  **Využití procesoru** nástroj nelze použít s aplikacemi pro Windows Phone Silverlight 8.1.  
  
 Tento názorný postup vás provede shromažďování a analýzy využití procesoru pro jednoduchou aplikaci Windows Universal XAML.  
  
##  <a name="BKMK_Create_the_CpuUseDemo_project"></a>Vytvoření projektu CpuUseDemo  
 **CpuUseDemo** je aplikace, která byla vytvořena pro ukazují, jak shromažďovat a analyzovat data o využití procesoru. Tlačítka Generovat číslo při volání metody, která vybere maximální hodnota z více volání funkce. Volaná funkce vytvoří velký počet náhodných hodnot a vrátí poslední. V textovém poli se zobrazí data.  
  
1.  Vytvoření nového jazyka C# univerzální pro Windows aplikace projektu s názvem **CpuUseDemo** pomocí **BlankApp** šablony.  
  
     ![Vytvořte CpuUseDemoProject](../profiling/media/cpu_use_newproject.png "CPU_USE_NewProject")  
  
2.  Nahraďte MainPage.xaml s [tento kód](#BKMK_MainPage_xaml).  
  
3.  Nahraďte MainPage.xaml.cs s [tento kód](#BKMK_MainPage_xaml_cs).  
  
4.  Sestavte aplikaci a vyzkoušejte ji. Tato aplikace je dostatečně jednoduchá, tak, aby zobrazovalo některé běžné případy analýzy dat využití procesoru.  
  
##  <a name="BKMK_Collect_CPU_usage_data"></a>Shromažďování údajů o využití procesoru  
 ![Spuštění sestavení pro vydání aplikace v simulátoru](../profiling/media/cpu_use_wt_setsimulatorandretail.png "CPU_USE_WT_SetSimulatorAndRetail")  
  
1.  V sadě Visual Studio, nastavte cíl nasazení na **simulátoru** a konfiguraci řešení **verze**.  
  
    -   Spuštění aplikace v simulátoru umožňuje snadno přepínat mezi Visual Studio IDE a aplikace.  
  
    -   Spuštění této aplikace v **verze** režimu nabízí lepší zobrazení skutečného výkonu aplikace.  
  
2.  Na **ladění** nabídce zvolte **profileru výkonu...** .  
  
3.  V výkon a diagnostiku rozbočovače, zvolte **využití procesoru** a potom zvolte **spustit**.  
  
     ![Spuštění relace diagnostiky CpuUsage](../profiling/media/cpu_use_wt_perfdiaghub.png "CPU_USE_WT_PerfDiagHub")  
  
4.  Při spuštění aplikace, klikněte na tlačítko **získat maximální počet**. Počkejte o sekundu poté, co se zobrazí výstup, a potom vyberte **získat maximální počet asynchronních**. Čekání na mezi kliknutí na tlačítko díky je jednodušší oddělit tlačítko klikněte na tlačítko rutiny v diagnostickou zprávu.  
  
5.  Jakmile se zobrazí na druhém řádku výstupu, zvolte **zastavit kolekce** v centru výkon a Diagnostika.  
  
 ![Zastavit shromažďování dat CpuUsage](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 Nástroj pro využití procesoru analyzuje data a zobrazí sestavu.  
  
 ![Sestava CpuUsage](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
##  <a name="BKMK_Analyze_the_CPU_Usage_report"></a>Analýza využití procesoru sestavy  
  
###  <a name="BKMK_CPU_utilization_timeline_graph"></a>Časová osa graf využití procesoru  
 ![CpuUtilization &#40; % &#41; Časová osa grafu](../profiling/media/cpu_use_wt_timelinegraph.png "CPU_USE_WT_TimelineGraph")  
  
 Graf využití procesoru obsahuje informace o aktivitě využití procesoru aplikace jako procento všech doba využití procesoru z všechna jádra procesoru na zařízení. Na počítači, dual-core nebyla shromážděna data této sestavy. Dva extrémní představují aktivity procesoru kliknutí na dva tlačítko. `GetMaxNumberButton_Click`provádí synchronně jednojádrový, takže má smysl, výška grafu metody nikdy přesahuje 50 %. `GetMaxNumberAsycButton_Click`Program spustí asynchronně mezi obě jader, tak, aby znovu vypadala právo, jeho Špička získá blíže využívá všechny prostředky procesoru na obou jader.  
  
####  <a name="BKMK_Select_timeline_segments_to_view_details"></a>Vyberte časové osy segmenty zobrazíte podrobnosti.  
 Použijte výběr řádky na **relace diagnostiky** časové osy a zaměřit se na GetMaxNumberButton_Click data:  
  
 ![GetMaxNumberButton &#95; Klikněte na vybrané](../profiling/media/cpu_use_wt_getmaxnumberreport.png "CPU_USE_WT_GetMaxNumberReport")  
  
 **Relace diagnostiky** časová osa nyní zobrazuje čas strávený v vybraný segment (trochu více než 2 sekundy v této sestavě) a filtry stromu volání na tyto metody, které byly spuštěny ve výběru.  
  
 Nyní vybrat `GetMaxNumberAsyncButton_Click` segmentu.  
  
 ![GetMaxNumberAsyncButton &#95; Klikněte na výběr sestavy](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 Tato metoda dokončení o druhou rychlejší než `GetMaxNumberButton_Click`, ale jsou méně zřejmé význam položky stromu volání.  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a>Využití procesoru stromu volání  
 Pokud chcete začít, vysvětlení volání stromu informace, vyberte znovu `GetMaxNumberButton_Click` segmentovat a podívejte se na podrobnosti o stromu hovoru.  
  
####  <a name="BKMK_Call_tree_structure"></a>Struktura stromu volání  
 ![GetMaxNumberButton &#95; Klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![Krok 1](../profiling/media/procguid_1.png "ProcGuid_1")|Uzel na nejvyšší úrovni ve stromech volání využití procesoru je pseudo uzel|  
|![Krok 2](../profiling/media/procguid_2.png "ProcGuid_2")|Ve většině aplikací když **zobrazit externí kód** možnost je vypnuta, je uzel druhé úrovně **[externí kód]** uzlu, který obsahuje systém a architektura kód, který spustí a ukončí aplikaci a nevykresluje uživatelského rozhraní, ovládací prvky plánování vláken a poskytuje jiných nízké úrovně služeb k aplikaci.|  
|![Krok 3](../profiling/media/procguid_3.png "ProcGuid_3")|Podřízené objekty daného uzlu druhé úrovně jsou metody uživatelského kódu a asynchronní rutiny, které jsou volány, nebo vytvořené druhé úrovně systému a framework kódu.|  
|![Krok 4](../profiling/media/procguid_4.png "ProcGuid_4")|Podřízené uzly metody obsahovat data jen pro volání metody nadřazené. Když **zobrazit externí kód** je zakázaná, metody aplikace může také obsahovat **[externí kód]** uzlu.|  
  
####  <a name="BKMK_External_Code"></a>Externí kódu  
 Externí kód se skládá z funkcí v systému a framework komponent, které se provádějí pomocí kódu, který můžete psát. Externí kód obsahuje funkce, které spuštění a zastavení aplikace, vykreslení uživatelského rozhraní, řídit vlákna a poskytují jiných nízké úrovně služeb k aplikaci. Ve většině případů nebude zájem o externí kód, a tak využití procesoru volání stromu shromáždí externí funkce metody uživatele do jedné **[externí kód]** uzlu.  
  
 Pokud chcete zobrazit cesty volání externí kódu, zvolte **zobrazit externí kód** z **filtrovat zobrazení** seznamu a potom zvolte **použít**.  
  
 ![Zvolte zobrazení filtru, a zobrazit externí kód](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 Mějte na paměti, že jsou vnořeny hluboko mnoho řetězy volání externí kód, tak, aby šířka sloupce název funkce může být vyšší než šířka zobrazení všech ale největší monitorování počítače. V takovém případě se zobrazují názvy funkcí jako **[...]** :  
  
 ![Vnořené externí kódu ve stromové struktuře volání](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 Použijte pole hledání najít uzel, který hledáte, a poté pomocí vodorovného posuvníku přenést data do zobrazení:  
  
 ![Vyhledávání pro vnořené externí kód](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a>Volání stromu datové sloupce  
  
|||  
|-|-|  
|**Celkové využití procesoru (%)**|![Celkový počet rovnice data %](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Procento procesoru aktivitu aplikace ve vybrané časové rozmezí, která byla použita ve volání funkce a funkce volané funkce. Všimněte si, že se to neliší od **využití procesoru** časová osa grafu, který porovnává celkovou aktivitu aplikace v časový rozsah a celkový počet dostupné kapacity procesoru.|  
|**Vlastního procesoru (%)**|![Vlastní % rovnice](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> Procento procesoru aktivitu aplikace ve vybrané časové rozmezí, která byla použita ve volání funkce, s výjimkou aktivitu funkce volané funkce.|  
|**Celkové využití procesoru (ms)**|Počet milisekund, po stráví ve volání funkce v vybraný časový rozsah a funkce, které byly volá funkci.|  
|**Vlastního procesoru (ms)**|Počet milisekund, po stráví ve volání funkce v vybraný časový rozsah a funkce, které byly volá funkci.|  
|**Modul**|Název modul, který obsahuje funkce, nebo počet modulů obsahující funkce v uzlu služby [externí kód].|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a>Asynchronní funkce ve využití procesoru stromu volání  
 Když kompilátor narazí asynchronní metodu, vytvoří třídu skrytá k řízení provádění metody. Třída je koncepčně, stav počítač, který obsahuje seznam generované kompilátorem funkce, které volají operace původní metody asynchronně, a zpětná volání, Plánovač a iterátory potřeby k nim správně. Při původní metoda je volána metodou nadřazeného, modulu runtime odebere metodu z nadřazeného objektu kontextu spuštění a spustí metody třídy skryté v kontextu systému a framework kód, který řídí spuštění aplikace. Asynchronní metody jsou často, ale ne vždy provést na jeden nebo více různých vláknech. Tento kód se zobrazí ve stromové struktuře využití procesoru volání jako podřízené objekty **[externí kód]** uzlu bezprostředně pod na nejvyšší uzel stromu.  
  
 Pokud chcete zobrazit tento v našem příkladu, znovu vyberte `GetMaxNumberAsyncButton_Click` segmentu v časovou osu.  
  
 ![GetMaxNumberAsyncButton &#95; Klikněte na výběr sestavy](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 První dva uzly v rámci **[externí kód]** generované kompilátorem metod třídy stav počítače. Třetí je volání původní metody. Rozšiřování generovaného metody se dozvíte, co se děje.  
  
 ![Rozšířené GetMaxNumberAsyncButton &#95; Klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click`nemá velmi málo; spravuje seznam hodnot úloh, vypočítá maximální počet výsledků a zobrazí výstup.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext`ukazuje, aktivity, které jsou potřebné k naplánování a spuštění 48 úlohy, které balí volání `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b`ukazuje aktivitu úlohy, které volají `GetNumber`.  
  
##  <a name="BKMK_Next_steps"></a>Další kroky  
 Aplikace CpuUseDemo není nejvíce špičkový aplikace, ale jeho nástroj můžete rozšířit pomocí a experimentovat s asynchronní operaci a dalších nástrojů v centru výkonu a Diagnostika.  
  
-   Všimněte si, že `MainPage::<GetNumberAsync>b__b` stráví v [externí kód] více času, než provede spuštění metody GetNumber. Velká část této doby je režii asynchronní operace. Pokuste se zvýšit počet úloh (nastavit `NUM_TASKS` konstantní z MainPage.xaml.cs) a snížit počet iterací v `GetNumber` (změnit `MIN_ITERATIONS` hodnotu). Spustit tento scénář kolekce a porovnání aktivitu procesoru `MainPage::<GetNumberAsync>b__b`do v původní relaci diagnostické využití procesoru. Zkuste to snižuje úkoly a zvýšení iterace.  
  
-   Uživatelé často nezáleží skutečné výkon vaší aplikace; jsou pro ně důležité dosahovaný výkon a odezvy aplikace. Přizpůsobivý uživatelského rozhraní jazyka XAML nástroj obsahuje podrobnosti aktivity ve vlákně UI, že platnost zaznamenatelného odezvy.  
  
     Vytvořit novou relaci v centru diagnostiky a výkonu a přidat nástroj reagující uživatelské rozhraní jazyka XAML a nástroj využití procesoru. Spusťte scénář kolekce. Pokud jste si přečetli to daleko, sestava pravděpodobně nemá zjistíte všechno, co nebyly se limitu, ale rozdíly v již započítáno **vlákna uživatelského rozhraní využití** je působivý časovou osu grafu pro tyto dvě metody. V komplexní, skutečné aplikace může být velmi užitečné kombinace nástroje.  
  
##  <a name="BKMK_MainPage_xaml"></a>MainPage.xaml  
  
```xaml  
<Page  
    x:Class="CpuUseDemo.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:CpuUseDemo"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Page.Resources>  
        <Style TargetType="TextBox">  
            <Setter Property="FontFamily"  Value="Lucida Console" />  
        </Style>  
    </Page.Resources>  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Grid.RowDefinitions>  
            <RowDefinition Height="Auto" />  
            <RowDefinition Height="*" />  
        </Grid.RowDefinitions>  
        <StackPanel Grid.Row="0" Orientation="Horizontal"  Margin="0,40,0,0">  
            <Button Name="GetMaxNumberButton" Click="GetMaxNumberButton_Click"  Content="Get Max Number" />  
            <Button Name="GetMaxNumberAsyncButton" Click="GetMaxNumberAsyncButton_Click"  Content="Get Max Number Async" />  
        </StackPanel>  
        <StackPanel Grid.Row="1">  
            <TextBox Name="TextBox1" AcceptsReturn="True" />  
        </StackPanel>  
    </Grid>  
  
</Page>  
  
```  
  
##  <a name="BKMK_MainPage_xaml_cs"></a>MainPage.xaml.cs  
  
```CSharp  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Linq;  
using System.Runtime.InteropServices.WindowsRuntime;  
using Windows.Foundation;  
using Windows.Foundation.Collections;  
using Windows.UI.Xaml;  
using Windows.UI.Xaml.Controls;  
using Windows.UI.Xaml.Controls.Primitives;  
using Windows.UI.Xaml.Data;  
using Windows.UI.Xaml.Input;  
using Windows.UI.Xaml.Media;  
using Windows.UI.Xaml.Navigation;  
using Windows.Foundation.Diagnostics;  
using System.Threading;  
using System.Threading.Tasks;  
using System.Collections.Concurrent;  
  
// The Blank Page item template is documented at http://go.microsoft.com/fwlink/?LinkId=234238  
  
namespace CpuUseDemo  
{  
    /// <summary>  
    /// An empty page that can be used on its own or navigated to within a Frame.  
    /// </summary>  
    public sealed partial class MainPage : Page  
    {  
        public MainPage()  
        {  
            this.InitializeComponent();  
        }  
  
        const int NUM_TASKS = 48;  
        const int MIN_ITERATIONS = int.MaxValue / 1000;  
        const int MAX_ITERATIONS = MIN_ITERATIONS + 10000;  
  
        long m_totalIterations = 0;  
        readonly object m_totalItersLock = new object();  
  
        private void GetMaxNumberButton_Click(object sender, RoutedEventArgs e)  
        {  
            GetMaxNumberAsyncButton.IsEnabled = false;  
            lock (m_totalItersLock)  
            {  
                m_totalIterations = 0;  
            }  
            List<int> tasks = new List<int>();  
            for (var i = 0; i < NUM_TASKS; i++)  
            {  
                var result = 0;  
                result = GetNumber();  
                tasks.Add(result);  
            }  
            var max = tasks.Max();  
            var s = GetOutputString("GetMaxNumberButton_Click", NUM_TASKS, max, m_totalIterations);  
            TextBox1.Text += s;  
            GetMaxNumberAsyncButton.IsEnabled = true;  
        }  
  
        private async void GetMaxNumberAsyncButton_Click(object sender, RoutedEventArgs e)  
        {  
            GetMaxNumberButton.IsEnabled = false;  
            GetMaxNumberAsyncButton.IsEnabled = false;  
            lock (m_totalItersLock)  
            {  
                m_totalIterations = 0;  
            }  
            var tasks = new ConcurrentBag<Task<int>>();  
            for (var i = 0; i < NUM_TASKS; i++)  
            {  
                tasks.Add(GetNumberAsync());  
            }  
            await Task.WhenAll(tasks.ToArray());  
            var max = 0;  
            foreach (var task in tasks)  
            {  
                max = Math.Max(max, task.Result);  
            }  
            var func = "GetMaxNumberAsyncButton_Click";  
            var outputText = GetOutputString(func, NUM_TASKS, max, m_totalIterations);  
            TextBox1.Text += outputText;  
            this.GetMaxNumberButton.IsEnabled = true;  
            GetMaxNumberAsyncButton.IsEnabled = true;  
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
  
        private Task<int> GetNumberAsync()  
        {  
            return Task<int>.Run(() =>  
            {  
                return GetNumber();  
            });  
        }  
  
        string GetOutputString(string func, int cycles, int max, long totalIters)  
        {  
            var fmt = "{0,-35}Tasks:{1,3}    Maximum:{2, 12}    Iterations:{3,12}\n";  
            return String.Format(fmt, func, cycles, max, totalIters);  
        }  
  
    }  
}  
  
```
## <a name="see-also"></a>Viz také
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)