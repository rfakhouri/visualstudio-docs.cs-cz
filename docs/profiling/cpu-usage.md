---
title: Analýza využití procesoru v aplikaci Visual Studio | Dokumentace Microsoftu
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
ms.openlocfilehash: 1409431b0cdaec775ecd420fb9b6ea1ded0868de
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2018
ms.locfileid: "42624172"
---
# <a name="analyze-cpu-usage"></a>Analýza využití procesoru
Když budete potřebovat zjistit problémy s výkonem ve vaší aplikaci, je dobrým začátkem pochopení, jak využívá procesor. **Využití procesoru** nástroj ukazuje, kde procesor tráví čas spuštění Visual C++, Visual C# nebo Visual Basic a kód jazyka JavaScript. Od verze Visual Studio 2015 Update 1, můžete zobrazit rozpis využití procesoru jednotlivých funkcích aniž byste museli opustit ladicí program. Můžete profilaci procesoru při ladění a vypnout a zobrazit výsledky, když se zastaví spuštění, například v na zarážce.  
  
Máte několik možností pro spouštění a správu diagnostickou relaci. Například můžete spustit **využití procesoru** nástroj na místních nebo vzdálených počítačích nebo na simulátoru nebo emulátoru. Můžete analyzovat výkon otevřít projekt v sadě Visual Studio, připojit k běžící aplikaci, nebo spusťte aplikaci, která se instaluje z Microsoft Store. Další informace najdete v tématu [spuštění nástroje pro profilaci s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md). 

Tady jsme ukazují, jak shromažďovat a analyzovat využití procesoru u sestavení pro vydání. Analýza využití procesoru při ladění, naleznete v tématu [příručka začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md).

Windows 7 nebo novější je nutné použít nástroje pro profilaci uvedené v tomto článku, který je [Profiler výkonu](../profiling/profiling-feature-tour.md).
  
##  <a name="collect-cpu-usage-data"></a>Shromažďovat data o využití procesoru  
  
1.  V sadě Visual Studio, nastavte konfigurace řešení na **vydání** a zvolte cíl nasazení.  
  
     ![Vyberte verzi a místní počítač](../profiling/media/cpuuse_selectreleaselocalmachine.png "CPUUSE_SelectReleaseLocalMachine")  
  
    -   Spuštění aplikace **vydání** režim poskytuje lepší přehled aplikace skutečný výkon vaší aplikace.  
  
    -   Spuštění aplikace v místním počítači nejlépe replikuje provádění nainstalované aplikace.  
  
    -   Pokud shromažďujete data ze vzdáleného zařízení, spusťte aplikaci přímo v zařízení a ne pomocí připojení ke vzdálené ploše.  
  
    -   Pro aplikace Windows Phone, shromažďovat data přímo z **zařízení** poskytuje nejaktuálnější data.  
  
2.  Na **ladění** nabídce zvolte **Profiler výkonu**.  
  
3.  Zvolte **využití procesoru** a klikněte na tlačítko **Start**.  
  
     ![Zvolte využití procesoru](../profiling/media/cpuuse_lib_choosecpuusage.png "CPUUSE_LIB_ChooseCpuUsage")  
  
4.  Při spuštění aplikace, klikněte na tlačítko **získat maximální počet**. Počkejte asi sekundy po výstupu se zobrazí, a pak zvolte **získat maximální číslo asynchronní**. Čekání mezi kliknutí na tlačítko vytvoří je jednodušší oddělit tlačítko klikněte rutiny v diagnostickou sestavu.  
  
5.  Až na druhém řádku výstupu se zobrazí, zvolte **zastavit shromažďování** v Centru pro výkon a Diagnostika.  
  
 ![Zastavit shromažďování dat CpuUsage](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 Nástroj využití CPU analyzuje data a zobrazí sestavu.  
  
 ![Sestava CpuUsage](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
## <a name="analyze-the-cpu-usage-report"></a>Analýza sestavy využití procesoru  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a> Využití procesoru strom volání  
 Abyste mohli začít Principy informace o volání stromu, klikněte `GetMaxNumberButton_Click` segmentovat a podívejte se na Podrobnosti stromu volání.  
  
####  <a name="BKMK_Call_tree_structure"></a> Struktura stromu volání  
 ![GetMaxNumberButton&#95;klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![1. krok](../profiling/media/procguid_1.png "ProcGuid_1")|Nejvyšší uzel ve stromech volání Využití procesoru je fiktivní.|  
|![2. krok](../profiling/media/procguid_2.png "ProcGuid_2")|Ve většině aplikací, ve kterých zakážete možnost **Zobrazit externí kód**, je v druhé úrovni uzel **[Externí kód]**, který obsahuje systémový kód a kód architektury, který spouští a zastavuje aplikaci, vykresluje uživatelské rozhraní, řídí plánování podprocesů a na nejnižší úrovni zajišťuje pro aplikaci další služby.|  
|![3. krok](../profiling/media/procguid_3.png "ProcGuid_3")|Uzlu druhé úrovně jsou podřízeny metody uživatelského kódu a asynchronní rutiny, které volá nebo vytváří systémový kód a kód architektury druhé úrovně.|  
|![4. krok](../profiling/media/procguid_4.png "ProcGuid_4")|Podřízené uzly metody obsahují jenom data pro volání nadřízené metody. Pokud zakážete **Zobrazit externí kód**, mohou metody aplikace obsahovat také uzel **[Externí kód]**.|  
  
####  <a name="BKMK_External_Code"></a> Externí kód  
 Externím kódem se rozumí funkce systémových komponent a komponent architektury, které jsou spouštěné vámi napsaným kódem. Externí kód zahrnuje funkce, které spouštějí a zastavují aplikaci, vykreslují uživatelské rozhraní, řídí dělení na podprocesy a na nejnižší úrovni zajišťuje pro aplikaci další služby. Ve většině případů nebudete zájem o externí kód, a proto využití procesoru volání stromu shromáždí externí funkce metody uživatele do jednoho **[externí kód]** uzlu.  
  
 Pokud chcete zobrazit volání cesty z externího kódu, zvolte **zobrazit externí kód** z **filtrovat zobrazení** seznamu a klikněte na tlačítko **použít**.  
  
 ![Vyberte zobrazení filtru, pak si ukážeme, externí kód](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 Myslete na to, že řetězy volání externího kódu je většinou hluboko vnořené, takže šířka sloupce Název funkce může na většině počítačových monitorů – s výjimkou těch největších – přesáhnout šířku zobrazení. Pokud k tomu dojde, názvy funkcí jsou zobrazeny jako **[...]** :  
  
 ![Vnořené externí kód ve stromu volání](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 Pomocí vyhledávacího pole vyhledejte uzel, který hledáte, pak použít vodorovný posuvník přenést data do zobrazení:  
  
 ![Hledat vnořené externí kód](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a> Volání stromu datové sloupce  
  
|||  
|-|-|  
|**Celkový čas procesoru (%)**|![Celkem % dat rovnice](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Procento procesoru aktivita aplikace ve vybraném časovém rozsahu, který byl použit volání funkce a funkce volané funkce. Všimněte si, že se liší od **využití výkonu procesoru** graf časové osy, která porovnává celkové aktivity aplikace na celková dostupná kapacita procesoru časový rozsah.|  
|**Vlastní čas procesoru (%)**|![Vlastní % rovnice](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> Procento procesoru aktivita aplikace ve vybraném časovém rozsahu, která byla použita ve volání funkce, s výjimkou aktivit funkce volané funkce.|  
|**Celkový čas procesoru (ms)**|Počet milisekund strávený ve volání funkce ve vybraném časovém rozsahu a funkce, které byly volány funkce.|  
|**Vlastní čas procesoru (ms)**|Počet milisekund strávený ve volání funkce ve vybraném časovém rozsahu a funkce, které volal funkci kromě aktivit funkce volané funkce.|  
|**Modul**|Název modulu, který obsahuje funkce, nebo počet modulů, který obsahuje funkce v uzlu [externí kód].|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a> Asynchronní funkce ve stromu volání využití procesoru  
 Když kompilátor narazí na asynchronní metodu, vytvoří třídu skryté k řízení provádění metody. Třída je koncepčně stavového stroje, který obsahuje seznam vygenerovaný kompilátorem funkce, které volají operace původní metody asynchronně, a zpětná volání, Plánovač a iterátory potřebných k provedení je správně. Při původní metody je volána metodou nadřazeného, modul runtime odebere z kontextu spuštění nadřazené metody a metody třídy skryté běží v kontextu systému a rozhraní framework kód, který řídí spuštění aplikace. Asynchronní metody jsou často, ale ne vždy spouštěny na jeden nebo více různých vláken. Tento kód se zobrazí ve stromu volání procesoru jako podřízené objekty **[externí kód]** uzel bezprostředně pod nejvyšší uzel stromu.  
  
 Tento údaj zobrazíte v našem příkladu, znovu vyberte `GetMaxNumberAsyncButton_Click` segment na časové ose.  
  
 ![GetMaxNumberAsyncButton&#95;Click report selection](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 První dva uzly v rámci **[externí kód]** způsoby kompilátorem generované třídy stav počítače. Třetí je volání na původní metodu. Generované metody rozšíření se dozvíte, co se děje.  
  
 ![Rozbalit GetMaxNumberAsyncButton&#95;klikněte na tlačítko volání stromu](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click` velmi malý; nemá spravuje seznam hodnot úloh, vypočítá maximální počet výsledků a zobrazí výstup.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext` ukazuje aktivit potřebných k naplánování a spuštění 48 úkoly, které obalují volání `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b` ukazuje aktivitu úloh, které volají `GetNumber`.
