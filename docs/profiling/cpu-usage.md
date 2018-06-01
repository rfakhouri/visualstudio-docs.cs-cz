---
title: Analýza využití procesoru v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7501a20d-04a1-480f-a69c-201524aa709d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b372d3d76153b5f5c885a6987d898cf55254b413
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477519"
---
# <a name="analyze-cpu-usage"></a>Analýza využití procesoru
Když potřebujete prozkoumat problémy s výkonem v aplikaci, je vhodné oddělení na zahájení pochopení, jak používá procesoru. **Využití procesoru** nástroj ukazuje, kde je procesoru výdaje čas provádění Visual C++, Visual C# nebo Visual Basic a kód jazyka JavaScript. Od verze Visual Studio 2015 Update 1, můžete zobrazit rozpis podle funkce využití procesoru bez opuštění ladicího programu. Můžete zapnout procesoru profilace zapnout a vypnout při ladění a zobrazit výsledky při spuštění je zastaveno, například zarážky.  
  
Máte několik možností pro spouštění a správu relace diagnostiky. Například můžete spustit **využití procesoru** nástroj na místních nebo vzdálených počítačích nebo na v simulátoru nebo emulátor. Můžete analyzovat výkon otevřít projekt v sadě Visual Studio, připojený k spuštěné aplikaci, nebo můžete spustit aplikaci, která je nainstalované ze služby Microsoft Store. Další informace najdete v tématu [spustit nástrojích pro profilaci s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

Zde jsme ukazují, jak shromažďovat a analyzovat využití procesoru s verzi sestavení. Analýza využití procesoru při ladění, najdete v tématu [začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md). 

> [!NOTE]
> U platforem .NET Core a ASP.NET Core nástroj Využití procesoru v současnosti neposkytuje přesné výsledky o přenosných souborech PDB. Proto raději použijte celé soubory PDB.
  
##  <a name="BKMK_Collect_CPU_usage_data"></a> Shromažďování údajů o využití procesoru  
  
1.  V sadě Visual Studio, nastavte konfiguraci řešení na **verze** a vyberte cíl nasazení.  
  
     ![Vyberte verzi a místní počítač](../profiling/media/cpuuse_selectreleaselocalmachine.png "CPUUSE_SelectReleaseLocalMachine")  
  
    -   Spuštění aplikace **verze** režimu nabízí lepší zobrazení skutečného výkonu aplikace.  
  
    -   Spuštění aplikace v místním počítači nejlépe replikuje provádění nainstalovanou aplikaci.  
  
    -   Pokud se shromažďování dat ze vzdáleného zařízení, spusťte aplikaci přímo na zařízení a ne prostřednictvím připojení ke vzdálené ploše.  
  
    -   Pro aplikace Windows Phone, shromažďování dat přímo z **zařízení** poskytuje nejaktuálnější data.  
  
2.  Na **ladění** nabídce zvolte **výkonu profileru**.  
  
3.  Zvolte **využití procesoru** a potom zvolte **spustit**.  
  
     ![Zvolte využití procesoru](../profiling/media/cpuuse_lib_choosecpuusage.png "CPUUSE_LIB_ChooseCpuUsage")  
  
4.  Při spuštění aplikace, klikněte na tlačítko **získat maximální počet**. Počkejte o sekundu poté, co se zobrazí výstup, a potom vyberte **získat maximální počet asynchronních**. Čekání na mezi kliknutí na tlačítko díky je jednodušší oddělit tlačítko klikněte na tlačítko rutiny v diagnostickou zprávu.  
  
5.  Jakmile se zobrazí na druhém řádku výstupu, zvolte **zastavit kolekce** v centru výkon a Diagnostika.  
  
 ![Zastavit shromažďování dat CpuUsage](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 Nástroj pro využití procesoru analyzuje data a zobrazí sestavu.  
  
 ![Sestava CpuUsage](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
## <a name="analyze-the-cpu-usage-report"></a>Analýza sestav o využití procesoru  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a> Využití procesoru stromu volání  
 Pokud chcete začít, vysvětlení volání stromu informace, vyberte znovu `GetMaxNumberButton_Click` segmentovat a podívejte se na podrobnosti o stromu hovoru.  
  
####  <a name="BKMK_Call_tree_structure"></a> Struktura stromu volání  
 ![GetMaxNumberButton&#95;klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![1. krok](../profiling/media/procguid_1.png "ProcGuid_1")|Nejvyšší uzel ve stromech volání Využití procesoru je fiktivní.|  
|![2. krok](../profiling/media/procguid_2.png "ProcGuid_2")|Ve většině aplikací, ve kterých zakážete možnost **Zobrazit externí kód**, je v druhé úrovni uzel **[Externí kód]**, který obsahuje systémový kód a kód architektury, který spouští a zastavuje aplikaci, vykresluje uživatelské rozhraní, řídí plánování podprocesů a na nejnižší úrovni zajišťuje pro aplikaci další služby.|  
|![3. krok](../profiling/media/procguid_3.png "ProcGuid_3")|Uzlu druhé úrovně jsou podřízeny metody uživatelského kódu a asynchronní rutiny, které volá nebo vytváří systémový kód a kód architektury druhé úrovně.|  
|![4. krok](../profiling/media/procguid_4.png "ProcGuid_4")|Podřízené uzly metody obsahují jenom data pro volání nadřízené metody. Pokud zakážete **Zobrazit externí kód**, mohou metody aplikace obsahovat také uzel **[Externí kód]**.|  
  
####  <a name="BKMK_External_Code"></a> Externí kódu  
 Externím kódem se rozumí funkce systémových komponent a komponent architektury, které jsou spouštěné vámi napsaným kódem. Externí kód zahrnuje funkce, které spouštějí a zastavují aplikaci, vykreslují uživatelské rozhraní, řídí dělení na podprocesy a na nejnižší úrovni zajišťuje pro aplikaci další služby. Ve většině případů nebude zájem o externí kód, a tak využití procesoru volání stromu shromáždí externí funkce metody uživatele do jedné **[externí kód]** uzlu.  
  
 Pokud chcete zobrazit cesty volání externí kódu, zvolte **zobrazit externí kód** z **filtrovat zobrazení** seznamu a potom zvolte **použít**.  
  
 ![Zvolte zobrazení filtru, a zobrazit externí kód](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 Myslete na to, že řetězy volání externího kódu je většinou hluboko vnořené, takže šířka sloupce Název funkce může na většině počítačových monitorů – s výjimkou těch největších – přesáhnout šířku zobrazení. V takovém případě se zobrazují názvy funkcí jako **[...]** :  
  
 ![Vnořené externí kódu ve stromové struktuře volání](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 Použijte pole hledání najít uzel, který hledáte, a poté pomocí vodorovného posuvníku přenést data do zobrazení:  
  
 ![Vyhledávání pro vnořené externí kód](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a> Volání stromu datové sloupce  
  
|||  
|-|-|  
|**Celkové využití procesoru (%)**|![Celkový počet rovnice data %](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Procento procesoru aktivitu aplikace ve vybrané časové rozmezí, která byla použita ve volání funkce a funkce volané funkce. Všimněte si, že se to neliší od **využití procesoru** časová osa grafu, který porovnává celkovou aktivitu aplikace v časový rozsah a celkový počet dostupné kapacity procesoru.|  
|**Vlastního procesoru (%)**|![Vlastní % rovnice](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> Procento procesoru aktivitu aplikace ve vybrané časové rozmezí, která byla použita ve volání funkce, s výjimkou aktivitu funkce volané funkce.|  
|**Celkové využití procesoru (ms)**|Počet milisekund, po stráví ve volání funkce v vybraný časový rozsah a funkce, které byly volá funkci.|  
|**Vlastního procesoru (ms)**|Počet milisekund, po stráví ve volání funkce v vybraný časový rozsah a funkce, které byly volá funkci, s výjimkou aktivitu funkce volané funkce.|  
|**Modul**|Název modul, který obsahuje funkce, nebo počet modulů obsahující funkce v uzlu služby [externí kód].|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a> Asynchronní funkce ve stromové struktuře volání využití procesoru  
 Když kompilátor narazí asynchronní metodu, vytvoří třídu skrytá k řízení provádění metody. Třída je koncepčně, stav počítač, který obsahuje seznam generované kompilátorem funkce, které volají operace původní metody asynchronně, a zpětná volání, Plánovač a iterátory potřeba správně spustit. Při původní metoda je volána metodou nadřazeného, modulu runtime odebere metodu z nadřazeného objektu kontextu spuštění a spustí metody třídy skryté v kontextu systému a framework kód, který řídí spuštění aplikace. Asynchronní metody jsou často, ale ne vždy provést na jeden nebo více různých vláknech. Tento kód se zobrazí ve stromové struktuře využití procesoru volání jako podřízené objekty **[externí kód]** uzlu bezprostředně pod na nejvyšší uzel stromu.  
  
 Pokud chcete zobrazit tento v našem příkladu, znovu vyberte `GetMaxNumberAsyncButton_Click` segmentu v časovou osu.  
  
 ![GetMaxNumberAsyncButton&#95;Click report selection](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 První dva uzly v rámci **[externí kód]** generované kompilátorem metod třídy stav počítače. Třetí je volání původní metody. Rozšiřování generovaného metody se dozvíte, co se děje.  
  
 ![Rozšířit GetMaxNumberAsyncButton&#95;klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click` nemá velmi málo; spravuje seznam hodnot úloh, vypočítá maximální počet výsledků a zobrazí výstup.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext` ukazuje, aktivity, které jsou potřebné k naplánování a spuštění 48 úlohy, které balí volání `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b` ukazuje aktivitu úlohy, které volají `GetNumber`.
