---
title: "Analýza využití paměti v sadě Visual Studio | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d6fc25c3a9d7306332c704453f22073df4e76546
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="profile-memory-usage-in-visual-studio"></a>Profil využití paměti v sadě Visual Studio
Najít nevracení paměti a neefektivní paměti při ladění pomocí integrované ladicí program **využití paměti** nástroj pro diagnostiku. Umožňuje nástroj využití paměti, proveďte jeden nebo více *snímky* spravovaná a nativní paměti haldy pro lepší porozumění tomu dopad využití paměti typy objektů. Můžete shromažďovat snímky .NET, nativní nebo smíšený režim (.NET a nativní) aplikace.  
  
 Následující grafické ukazuje **diagnostické nástroje** okno (k dispozici ve Visual Studiu 2015 Update 1 nebo novější):  
  
 ![DiagnosticTools & č. 45; Aktualizaci1](../profiling/media/diagnostictools-update1.png "DiagnosticTools aktualizaci1")  
  
 I když můžete shromažďovat snímky paměti v kdykoli **využití paměti** nástroj ladicího programu sady Visual Studio můžete použít k řízení, jak se aplikace spustí při zkoumání problémů s výkonem. Nastavení zarážek krokování, přerušení všech akcí a další ladicí program můžete zaměřit vaši vyšetřování výkonu na cesty kódu, které jsou nejdůležitější. Provedení těchto akcí, když aplikace běží, můžete eliminovat šumu z kód, který není vás zajímají a může výrazně snížit dobu potřebnou k diagnostikovat problém.  
  
 Můžete také použít nástroj paměti mimo ladicí program. V tématu [využití paměti bez ladění](../profiling/memory-usage-without-debugging2.md).  
  
> [!NOTE]
>  **Vlastní podporu Allocator** nativní paměti profileru funguje tak, že shromažďování přidělení [trasování událostí pro Windows](/windows-hardware/drivers/devtest/event-tracing-for-windows--etw-) událostí datech vysílaných za běhu.  Alokátorů v CRT a sady Windows SDK mít byla poznámky na úrovni zdroje. tak, aby jejich přidělení data se dají zachytit.  Pokud píšete vlastní alokátorů, pak všechny funkce, které vrací ukazatel do nově přidělených halda paměti může být doplněny pomocí [__declspec](/cpp/cpp/declspec)(allocator), jak je vidět v tomto příkladu pro myMalloc:  
>   
>  `__declspec(allocator) void* myMalloc(size_t size)` 

## <a name="collect-memory-usage-data"></a>Shromažďování údajů o využití paměti

1.  Otevřete projekt, který chcete ladit v sadě Visual Studio a nastavit zarážky ve vaší aplikaci v místě, kde chcete začít zkoumání využití paměti.

    Pokud máte oblasti, kde máte podezření paměti problém, nastavte první zarážky předtím, než dojde k problému paměti.

    > [!TIP]
    >  Vzhledem k tomu může být náročné k zaznamenání profilu paměti operace, která vás zajímá, když vaše aplikace často přiděluje a zrušte přidělí paměť, nastavte zarážky na začátku a konci operace (nebo krok prostřednictvím operaci) a zjistit, že že přesný bod, který paměť změnit. 

2.  Druhý zarážku na konci funkce nebo kód, který chcete analyzovat oblasti (nebo po výskytu problému možného paměti).
  
3.  **Diagnostické nástroje** okno se automaticky zobrazí, pokud jste vypnuli ho. Zobrazte okno znovu, klikněte na tlačítko **ladění / Windows / zobrazit diagnostické nástroje**.

4.  Zvolte **využití paměti** s **vyberte nástroje** nastavení na panelu nástrojů.

     ![Zobrazit nástroje pro diagnostiku](../profiling/media/DiagToolsSelectTool.png "DiagToolsSelectTool")

5.  Klikněte na tlačítko **ladění / spusťte ladění** (nebo **spustit** na panelu nástrojů nebo **F5**).

     Po dokončení nahrávání aplikace se zobrazí přehled o diagnostické nástroje.

     ![Diagnostické nástroje kartu Souhrn](../profiling/media/DiagToolsSummaryTab.png "DiagToolsSummaryTab")

     > [!NOTE]
     >  Protože shromažďování paměti, že data mohou ovlivnit výkon ladění aplikací pro nativní nebo ve smíšeném režimu, jsou ve výchozím nastavení zakázané snímky paměti. Povolit snímky v aplikacích pro nativní nebo ve smíšeném režimu, spusťte relaci ladění (klávesovou zkratku: **F5**). Když **diagnostické nástroje** se zobrazí v okně vyberte na kartě využití paměti a potom vyberte **profilace haldy**.  
     >   
     >  ![Povolit snímky](../profiling/media/dbgdiag_mem_mixedtoolbar_enablesnapshot.png "DBGDIAG_MEM_MixedToolbar_EnableSnapshot")  
     >   
     >  Zastavit (klávesovou zkratku: **Shift + F5**) a znovu spusťte ladění.  

6.  K pořízení snímku na začátku relaci ladění, zvolte **trvat snímek** na **využití paměti** souhrnné panelu nástrojů. (Ho mohou pomoci nastavit zarážky zde také).

    ![Trvat snímek](../profiling/media/dbgdiag_mem_mixedtoolbar_takesnapshot.png "DBGDIAG_MEM_MixedToolbar_TakeSnapshot") 
     
     > [!TIP]
     >  Chcete-li vytvořit směrný plán pro porovnání paměti, zvažte pořízení snímku na začátku relaci ladění.  

6.  Spusťte scénář, který způsobí, že vaše první zarážky být narazí.

7.  Při první zarážky bylo pozastaveno ladicího programu, zvolte **trvat snímek** na **využití paměti** souhrnné panelu nástrojů.  

8.  Stiskněte F5 a spusťte aplikaci k vaší zarážce druhý.

9.  Nyní vytvořte nový snímek.

     V tomto okamžiku můžete začít analyzovat data.    
  
## <a name="analyze-memory-usage-data"></a>Analyzovat data o využití paměti
Řádky tabulku souhrnu využití paměti uvádí snímků, které jste provedli během ladicí relace a nabízí odkazy na podrobnější zobrazení.

![Tabulka souhrnu paměti](../profiling/media/dbgdiag_mem_summarytable.png "DBGDIAG_MEM_SummaryTable")

 Název sloupce, které závisí na režim ladění, zvolte ve vlastnostech projektu: .NET, nativní nebo smíšená (.NET a nativní).  
  
-   **Objekty (rozdílové)** a **přidělení (rozdílové)** sloupců zobrazit počet objektů v rozhraní .NET a nativní paměti při pořízení snímku.  
  
-   **Velikost haldy (rozdílové)** sloupec zobrazuje počet bajtů v rozhraní .NET a nativní hald 

Pokud jste provedli několik snímků, zahrnují buněk tabulku souhrnu změnu v hodnotě mezi řádek snímku a předchozí snímek.  

Chcete-li analýza využití paměti, klikněte na jeden z odkazů, které se otevře podrobnou zprávu o využití paměti:  

-   Chcete-li zobrazit podrobnosti o rozdíl mezi snímek aktuální a předchozí snímek, vyberte odkaz změnit nalevo od šipku (![zvýšit využití paměti](../profiling/media/prof-tour-mem-usage-up-arrow.png "zvýšit využití paměti")). Označené červenou šipkou označuje zvýšení využití paměti a zelenou šipku na znamená snížení.

    > [!TIP]
    >  K identifikaci problémů paměti rychleji, rozdílové sestavy jsou seřazené podle typy objektů, které zvýšily nejvíce v celkový počet (klikněte na odkaz změnit v **objekty (rozdílové)** sloupec) nebo který vyšší nejvíce v celkovou velikost haldy (klikněte na odkaz změnit v **velikost haldy (rozdílové)** sloupce).

-   Chcete-li zobrazit podrobnosti o pouze vybraný snímek, klikněte na odkaz nebyla změněna. 
  
 Sestava se zobrazí v samostatném okně.   
  
### <a name="managed-types-reports"></a>Spravované typy sestav  
 Vyberte aktuální odkaz **objekty (rozdílové)** nebo **přidělení (rozdílové)** buňku v tabulce shrnutí, využití paměti.  
  
 ![Ladicí program spravovaný typ sestavy & č. 45; Cesty, které se kořenový](../profiling/media/dbgdiag_mem_managedtypesreport_pathstoroot.png "DBGDIAG_MEM_ManagedTypesReport_PathsToRoot")  
  
 Horní podokno zobrazuje počet a velikost typy ve snímku, včetně velikosti všech objektů, které se odkazuje typ (**(včetně). velikost**).  
  
 **Cest k kořenové** stromu v dolním podokně zobrazí objekty, které odkazují na vybraném v horním podokně typu. Uvolňování paměti rozhraní .NET Framework vyčistí paměti pro objekt jenom v případě, že byla vydána poslední typ, který odkazuje.  
  
 **Odkazuje typy** Strom zobrazuje odkazy, které jsou uložené ve vybraném v horním podokně typu.  
  
 ![Spravované eferenced typy zobrazení sestavy](../profiling/media/dbgdiag_mem_managedtypesreport_referencedtypes.png "DBGDIAG_MEM_ManagedTypesReport_ReferencedTypes")  
  
 V horním podokně zobrazit instance vybraného typu, vyberte ![Instance ikonu](../profiling/media/dbgdiag_mem_instanceicon.png "DBGDIAG_MEM_InstanceIcon") ikonu.  
  
 ![Zobrazení instancí](../profiling/media/dbgdiag_mem_managedtypesreport_instances.png "DBGDIAG_MEM_ManagedTypesReport_Instances")  
  
 **Instance** zobrazení ve snímku v horním podokně zobrazí instance vybraný objekt. Cesty do podokna kořenové a odkazuje typy zobrazit objekty, které odkazují ve vybrané instanci a typy, které odkazuje na vybranou instanci. Po zastavení ladicího programu v okamžiku, kdy pořízení snímku najedete můžete hodnotu buňky pro zobrazení hodnot z objektu v popisu tlačítka.  
  
### <a name="native-type-reports"></a>Nativní typ sestavy  
 Vyberte aktuální odkaz **přidělení (rozdílové)** nebo **velikost haldy (rozdílové)** buňky v souhrnné tabulce využití paměti **diagnostické nástroje** okno.  
  
 ![Nativní typ zobrazení](../profiling/media/dbgdiag_mem_native_typesview.png "DBGDIAG_MEM_Native_TypesView")  
  
 **Typy zobrazení** zobrazí počet a velikost typy ve snímku.  
  
-   Zvolte ikonu instancí (![ikonu instance ve sloupci Typ objektu](../profiling/media/dbg_mma_instancesicon.png "DBG_MMA_InstancesIcon")) z vybraného typu zobrazíte informace o objektech vybraného typu ve snímku.  
  
     **Instance** zobrazení zobrazí každou instanci daného typu. Výběr instance zobrazí, jejichž výsledkem vytvoření instance v zásobníku volání **přidělení zásobníku volání** podokně.  
  
     ![Zobrazení instancí](../profiling/media/dbgdiag_mem_native_instances.png "DBGDIAG_MEM_Native_Instances")  
  
-   Zvolte **zásobníky zobrazení** v **režimu zobrazení** seznamu zobrazíte přidělení zásobníku pro vybraný typ.  
  
     ![Balíků zobrazení](../profiling/media/dbgdiag_mem_native_stacksview.png "DBGDIAG_MEM_Native_StacksView")  
  
### <a name="change-diff-reports"></a>Změnit sestavy (rozdílové)  
  
-   Vyberte odkaz změnit v buňce souhrnné tabulky **využití paměti** na kartě **diagnostické nástroje** okno.  
  
     ![Zvolte změnu &#40; dif &#41; f sestavy](../profiling/media/dbgdiag_mem_choosediffreport.png "DBGDIAG_MEM_ChooseDiffReport")  
  
-   Zvolte snímku v **porovnat k** seznam spravovaným nebo nativním sestavy.  
  
     ![Zvolte ze seznamu porovnat do snímku](../profiling/media/dbgdiag_mem_choosecompareto.png "DBGDIAG_MEM_ChooseCompareTo")  
  
 Sestava změn přidá sloupce (označené jako **(rozdílové)**) základní sestavy, které tento rozdíl mezi hodnotou základní snímku a porovnání snímku. Zde je, jak může vypadat sestavy rozdílové nativní typ zobrazení:  
  
 ![Nativní typy rozdílové Veiw](../profiling/media/dbgdiag_mem_native_typesviewdiff.png "DBGDIAG_MEM_Native_TypesViewDiff")  
  
## <a name="blogs-and-videos"></a>Blogy a videa  

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171) o používání nástroje diagnostiky, které ukazuje, jak analyzovat využití paměti a využití procesoru v aplikaci Visual Studio 2017. |

 [Analýza využití procesoru a paměti při ladění](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Visual C++ Blog: Profilace paměti ve Visual C++ 2015](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="see-also"></a>Viz také
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)