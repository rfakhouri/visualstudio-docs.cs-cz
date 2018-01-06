---
title: "Analýza využití procesoru v sadě Visual Studio | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7501a20d-04a1-480f-a69c-201524aa709d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eabbb315d03a6ba69d80d46276b0b6dff5846693
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="analyze-cpu-usage"></a>Analýza využití procesoru
Když potřebujete prozkoumat problémy s výkonem v aplikaci, je vhodné oddělení na zahájení pochopení, jak používá procesoru. **Využití procesoru** nástroj ukazuje, kde je procesoru výdaje čas provádění Visual C++, Visual C# nebo Visual Basic a kód jazyka JavaScript. Od verze Visual Studio 2015 Update 1, můžete zobrazit rozpis podle funkce využití procesoru bez opuštění ladicího programu. Můžete zapnout procesoru profilace zapnout a vypnout při ladění a zobrazit výsledky při spuštění je zastaveno, například zarážky.  
  
Máte několik možností pro spouštění a správu relace diagnostiky. Například můžete spustit **využití procesoru** nástroj na místních nebo vzdálených počítačích nebo na v simulátoru nebo emulátor. Můžete analyzovat výkon otevřít projekt v sadě Visual Studio, připojený k spuštěné aplikaci, nebo můžete spustit aplikaci, která je nainstalované ze služby Microsoft Store. Další informace najdete v tématu [spustit nástrojích pro profilaci s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md). Návod, která analyzuje výkon aplikací UWP najdete v tématu [analýza využití procesoru v aplikaci UWP (Universal Windows)](analyze-cpu-usage-in-a-windows-universal-app.md). 

Zde jsme ukazují, jak shromažďovat a analyzovat využití procesoru s verzi sestavení. Analýza využití procesoru při ladění, najdete v tématu [začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md). 
  
##  <a name="BKMK_Collect_CPU_usage_data"></a>Shromažďování údajů o využití procesoru  
  
1.  V sadě Visual Studio, nastavte konfiguraci řešení na **verze** a vyberte cíl nasazení.  
  
     ![Vyberte verzi a místní počítač](../profiling/media/cpuuse_selectreleaselocalmachine.png "CPUUSE_SelectReleaseLocalMachine")  
  
    -   Spuštění aplikace **verze** režimu nabízí lepší zobrazení skutečného výkonu aplikace.  
  
    -   Spuštění aplikace v místním počítači nejlépe replikuje provádění nainstalovanou aplikaci.  
  
    -   Pokud se shromažďování dat ze vzdáleného zařízení, spusťte aplikaci přímo na zařízení a ne prostřednictvím připojení ke vzdálené ploše.  
  
    -   Pro aplikace Windows Phone, shromažďování dat přímo z **zařízení** poskytuje nejaktuálnější data.  
  
2.  Na **ladění** nabídce zvolte **profileru výkonu...** .  
  
3.  Zvolte **využití procesoru** a potom zvolte **spustit**.  
  
     ![Zvolte využití procesoru](../profiling/media/cpuuse_lib_choosecpuusage.png "CPUUSE_LIB_ChooseCpuUsage")  
  
4.  Při spuštění aplikace, klikněte na tlačítko **získat maximální počet**. Počkejte o sekundu poté, co se zobrazí výstup, a potom vyberte **získat maximální počet asynchronních**. Čekání na mezi kliknutí na tlačítko díky je jednodušší oddělit tlačítko klikněte na tlačítko rutiny v diagnostickou zprávu.  
  
5.  Jakmile se zobrazí na druhém řádku výstupu, zvolte **zastavit kolekce** v centru výkon a Diagnostika.  
  
 ![Zastavit shromažďování dat CpuUsage](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 Nástroj pro využití procesoru analyzuje data a zobrazí sestavu.  
  
 ![Sestava CpuUsage](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
## <a name="analyze-the-cpu-usage-report"></a>Analýza využití procesoru sestavy  
  
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
 Externí kódu jsou funkcí v systému a framework komponenty, provedený kód napíšete. Externí kód zahrnují funkce, které spuštění a zastavení aplikace, vykreslení uživatelského rozhraní, řídit vlákna a poskytují jiných nízké úrovně služeb k aplikaci. Ve většině případů nebude zájem o externí kód, a tak využití procesoru volání stromu shromáždí externí funkce metody uživatele do jedné **[externí kód]** uzlu.  
  
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
 Když kompilátor narazí asynchronní metodu, vytvoří třídu skrytá k řízení provádění metody. Třída je koncepčně, stav počítač, který obsahuje seznam generované kompilátorem funkce, které volají operace původní metody asynchronně, a zpětná volání, Plánovač a iterátory potřeba správně spustit. Při původní metoda je volána metodou nadřazeného, modulu runtime odebere metodu z nadřazeného objektu kontextu spuštění a spustí metody třídy skryté v kontextu systému a framework kód, který řídí spuštění aplikace. Asynchronní metody jsou často, ale ne vždy provést na jeden nebo více různých vláknech. Tento kód se zobrazí ve stromové struktuře využití procesoru volání jako podřízené objekty **[externí kód]** uzlu bezprostředně pod na nejvyšší uzel stromu.  
  
 Pokud chcete zobrazit tento v našem příkladu, znovu vyberte `GetMaxNumberAsyncButton_Click` segmentu v časovou osu.  
  
 ![GetMaxNumberAsyncButton &#95; Klikněte na výběr sestavy](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 První dva uzly v rámci **[externí kód]** generované kompilátorem metod třídy stav počítače. Třetí je volání původní metody. Rozšiřování generovaného metody se dozvíte, co se děje.  
  
 ![Rozšířené GetMaxNumberAsyncButton &#95; Klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click`nemá velmi málo; spravuje seznam hodnot úloh, vypočítá maximální počet výsledků a zobrazí výstup.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext`ukazuje, aktivity, které jsou potřebné k naplánování a spuštění 48 úlohy, které balí volání `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b`ukazuje aktivitu úlohy, které volají `GetNumber`.
