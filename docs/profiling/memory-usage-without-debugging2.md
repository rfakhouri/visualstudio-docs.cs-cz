---
title: Analýza využití paměti bez ladicí program VS | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fc133ee89c61146ab5217e5b48f4c9cacff5aaf0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-memory-usage-without-the-visual-studio-debugger"></a>Analýza využití paměti bez ladicího programu sady Visual Studio
Můžete použít **využití paměti** nástroje bez ladění proveďte následující  
  
-   Monitorování vaší aplikace paměti při vývoji scénáři použití vpravo v sadě Visual Studio.  
  
-   Vytvořte podrobná snímky stavu paměti vaší aplikace.  
  
-   Porovnejte snímky najít hlavní příčinu problémů s pamětí.  
  
 Toto téma popisuje, jak použít nástroj využití paměti pro analýzu aplikace UWP XAML. Pokud chcete analýza využití paměti v aplikaci UWP, která používá JavaScript a HTML najdete v tématu [analýza využití paměti (JavaScript)](../profiling/javascript-memory.md).  
  
##  <a name="BKMK_Start_a_Memory_Usage_diagnostic_session"></a> Spustit diagnostické relaci využití paměti  
  
1.  Otevřete projekt C# Universal Windows v sadě Visual Studio.  
  
2.  Na řádku nabídek zvolte **ladění nebo profileru výkonu...** .  
  
3.  Vyberte **využití paměti** a potom zvolte **spustit** tlačítko v dolní části stránky.  
  
     ![Spustit diagnostické relaci využití paměti](../profiling/media/memuse_start_diagnosticssession.png "MEMUSE_Start_DiagnosticsSession")  
  
##  <a name="BKMK_Monitor_memory_use"></a> Monitorování využití paměti  
 Přestože je možné použít **využití paměti** nástroje generovat podrobné sestavy, které vám pomůže najít a opravit problémy, můžete ji použít i k účinky v reálném čase paměti scénáři aktivně vyvíjíte.  
  
 Při spuštění relace diagnostiky spuštění vaší aplikace a **diagnostické nástroje** okně se zobrazí graf časová osa využití paměti vaší aplikace.  
  
 ![Stránka s přehledem využití paměti](../profiling/media/memuse__reportoverview.png "MEMUSE__ReportOverview")  
  
 Časová osa grafu ukazuje kolísání paměti vaše aplikace běží. Špičky v grafu obvykle znamenat, že nějaký kód je shromažďování nebo vytváření dat a pak zahození po dokončení zpracování. Extrémní označují oblasti, které je možné k optimalizaci. Další zájmu je zvýšení využití paměti, která nevrátí, protože může to znamenat využití neefektivní paměti nebo i nevrácenou pamětí.  
  
###  <a name="BKMK_Close_a_monitoring_session"></a> Zavřete relaci monitorování  
 ![Zastavit sběr](../profiling/media/memuse__stopcollection.png "MEMUSE__StopCollection")  
  
 Chcete-li ukončit relaci sledování bez vytváření sestavy, právě zavřete okno diagnostiky. Chcete-li vygenerovat sestavu, pokud jste pořídili snímky paměti, zvolte **Zastavit**.  
  
##  <a name="BKMK_Take_snapshots_to_analyze_the_memory_state_of_your_app"></a> Pořízení snímků je stav paměti aplikace  
 Pokud zjistíte paměti problém, který chcete prozkoumat, může trvat snímky během relace diagnostiky k zachycení objekty v paměti v konkrétní situacích. Protože se některá aplikace používá velký počet mnoho typů objektů, můžete chtít analýzy soustředit se jenom na jeden scénář. Je také vhodné k vytvoření standardních hodnot výpisu aplikace předtím, než se zobrazí chybu paměti, nový snímek po prvním výskytem problému a jeden nebo více další snímky Pokud scénáři, můžete opakovat.  
  
 Shromažďování snímků, zahájit novou relaci diagnostiky. Zvolte **trvat snímku** Pokud chcete zaznamenání dat o paměti. Chcete-li vygenerovat sestavu, zvolte **Zastavit**.  
  
##  <a name="BKMK_Memory_Usage_overview_page"></a> Stránka s přehledem využití paměti  
 Poté, co zastavíte shromažďování dat, nástroj využití paměti ukončí aplikaci a zobrazí přehled sestavy.  
  
 ![Stránka s přehledem využití paměti](../profiling/media/memuse__reportoverview.png "MEMUSE__ReportOverview")  
  
###  <a name="BKMK_Memory_Usage_snapshot_views"></a> Zobrazení snímku využití paměti  
 Otevřete podrobné sestavy v systému windows nové sady Visual Studio používáte zobrazení snímku. Existují dva typy snímků zobrazení:  
  
-   A [snímku podrobnosti sestavy](../profiling/memory-usage-without-debugging2.md#BKMK_Snapshot_details_reports) zobrazuje typy a instance v jeden snímek.  
  
-   A [snímek sestavy rozdíl (rozdílové)](../profiling/memory-usage-without-debugging2.md#BKMK_Snapshot_difference__diff__reports) porovná typy a instance v dva snímky.  
  
 ![Pořízení snímku zobrazení odkazy](../profiling/media/memuse__snapshotview_numbered.png "MEMUSE__SnapshotView_Numbered")  
  
 Číslované položky na obrázku snímku zobrazení jsou odkazy, které otevřete zobrazení sestav využití paměti.  
  
|||  
|-|-|  
|![Krok 1](../profiling/media/procguid_1.png "ProcGuid_1")|Text odkazu zobrazuje celkový počet bajtů v paměti, když pořízení snímku.<br /><br /> Vyberte tento odkaz na Zobrazit sestavu Podrobnosti snímku seřazených podle celková velikost instance typu.|  
|![Krok 2](../profiling/media/procguid_2.png "ProcGuid_2")|Text odkazu zobrazuje celkový počet objektů v paměti, když pořízení snímku.<br /><br /> Vyberte tento odkaz na Zobrazit sestavu Podrobnosti snímku seřazených podle počtu instancí typy.|  
|![Krok 3](../profiling/media/procguid_3.png "ProcGuid_3")|Text odkazu ukazuje rozdíl mezi celková velikost objektů v paměti v tuto chvíli tento snímek a celková velikost předchozí snímek.<br /><br /> Text odkazu je kladné číslo, když tento snímek velikost paměti je větší než předchozí a na záporné číslo, když velikost je menší. Text odkazu **směrného plánu** označuje, že tento snímek je první v relace diagnostiky; **Žádný rozdíl** označuje, že rozdíl je nula.<br /><br /> Vyberte tento odkaz na Zobrazit sestavu rozdílové snímku seřazených podle rozdíl ve celková velikost instance typy.|  
|![Krok 4](../profiling/media/procguid_4.png "ProcGuid_4")|Text odkazu ukazuje rozdíl mezi celkový počet paměťových objektech v tento snímek a počet objektů v předchozí snímek.<br /><br /> Vyberte tento odkaz na Zobrazit sestavu rozdílové snímku seřazených podle rozdíl ve celkový počet instancí typy.|  
  
##  <a name="BKMK_Snapshot_reports"></a> Snímku sestavy  
 ![Využití paměti snímek sestavy](../profiling/media/memuse_snapshotreport_all.png "MEMUSE_SnapshotReport_All")  
  
###  <a name="BKMK_Snapshot_report_trees"></a> Stromy snímku sestavy  
  
####  <a name="BKMK_Managed_Heap"></a> Spravovaná halda  
 Spravovaná halda stromu [stromu spravované haldy (snímku podrobnosti)](../profiling/memory-usage-without-debugging2.md#BKMK_Managed_Heap_tree__Snapshot_details_) a [stromu spravované haldy (snímku rozdílové)](../profiling/memory-usage-without-debugging2.md#BKMK_Managed_Heap_tree__Snapshot_diff_) zobrazit typy a instance v sestavě. Výběr typu nebo instance zobrazí **cest k kořenové** a **odkazuje objekty** stromy pro vybranou položku.  
  
####  <a name="BKMK_Paths_to_Root"></a> Cesty, které se kořenový  
 [Cesty do stromu kořenové (snímku podrobnosti)](../profiling/memory-usage-without-debugging2.md#BKMK_Paths_to_Root_tree__Snapshot_details_) a [cesty do stromu kořenové (snímku rozdílové)](../profiling/memory-usage-without-debugging2.md#BKMK_Paths_to_Root_tree__Snapshot_diff_) zobrazit řetězu objektů, které odkazují na typ, nebo instance. Uvolňování paměti rozhraní .NET Framework vyčistí paměti pro objekt jenom v případě, že byly vydány všechny odkazy na ni.  
  
####  <a name="BKMK_Referenced_Objects"></a> Odkazované objekty  
 [Stromu odkazuje objekty (snímku podrobnosti)](../profiling/memory-usage-without-debugging2.md#BKMK_Referenced_Objects_tree__Snapshot_details_) a [stromu odkazuje objekty (snímku rozdílové)](../profiling/memory-usage-without-debugging2.md#BKMK_Referenced_Objects_tree__Snapshot_diff_) zobrazit objekty, které odkazuje na vybraný typ nebo instance.  
  
###  <a name="BKMK_Object_Type_and_Instance_fields"></a> Typ objektu a Instance pole  
 Když **typ objektu** položka má podřízené položky, můžete na ikonu šipky k jejich zobrazení. Pokud barva **typ objektu** text je modrá, můžete ho přejděte na objekt v jeho souboru se zdrojovým kódem. Zdrojový soubor se otevře v samostatném okně.  
  
 Názvy instancí jsou jedinečná ID, které jsou generovány nástrojem pro využití paměti.  
  
 Pokud si všimnete typ, který nelze snadno identifikovat, nebo pokud nevíte, jak je zahrnuta ve vašem kódu, je pravděpodobně objekt z rozhraní .NET Framework, operační systém nebo kompilátoru, která nástroj využití paměti se zobrazí, protože je součástí vlastnictví řetězců vašich objektů.  
  
###  <a name="BKMK_Report_tree_filters_"></a> Filtry sestavy stromu  
 Většina aplikací obsahovat překvapivě velký počet různých typů, většina z nich velmi zajímavé pro vývojáře aplikace. **Využití paměti** nástroj definuje dva filtry, které můžete použít ke skrytí většinu těchto typů v **spravovaná halda** a **cest k kořenové** stromy. Můžete také filtrovat stromu název typu.  
  
 ![Možnosti třídění a filtrování](../profiling/media/memuse_sortandfilter.png "MEMUSE_SortAndFilter")  
  
####  <a name="BKMK_Filter"></a> Filtr  
 Zadejte řetězec ve **filtru** pole omezit stromu zobrazuje na typy, které obsahují zadaný text. Filtr není velká a malá písmena a rozpozná zadaný řetězec v žádné části názvy typů.  
  
####  <a name="BKMK_Collapse_Small_Objects"></a> Sbalit malých objektů  
 Když tento filtr je použit, jehož typy **velikost (bajty)** je menší než 0,5 procent celkové velikosti paměti snímku se v skryté **spravovaná halda** seznamu.  
  
####  <a name="BKMK_Just_My_Code"></a> Pouze můj kód  
 **Pouze můj kód** filtru skryje většina instancí, které jsou generovány nástrojem externí kódu. Externí typy patří v operačním systému nebo součástí architektury, nebo jsou generované kompilátorem.  
  
##  <a name="BKMK_Snapshot_details_reports"></a> Podrobnosti snímku sestavy  
 Použijete snímek podrobnosti sestavy a zaměřit se na jeden snímek z relace diagnostiky. Otevřete sestavu podrobnosti, vyberte jednu z odkazů v zobrazení snímku, jak je znázorněno na následujícím obrázku. Obě odkaz otevře stejné sestavě; jediným rozdílem je výchozí pořadí řazení **spravovaná halda** stromu v sestavě. V obou případech můžete změnit pořadí řazení po sestava se otevře.  
  
 ![Odkazy na snímek sestavy v zobrazení snímku](../profiling/media/memuse_snapshotview_snapshotdetailslinks.png "MEMUSE_SnapshotView_SnapshotDetailsLinks")  
  
-   **MB** odkaz seřadí sestava podle **(včetně). velikost (bajty)** sloupce.  
  
-   **Objekty** odkaz seřadí sestava podle **počet** sloupce.  
  
###  <a name="BKMK_Managed_Heap_tree__Snapshot_details_"></a> Spravovaná halda stromu (snímku podrobnosti)  
 **Spravovaná halda** stromu jsou uvedeny typy objektů, které jsou uložené v paměti. Můžete rozbalit název typu zobrazíte deset největší instance typu, seřazené podle velikosti. Výběr typu nebo instance zobrazí **cest k kořenové** a **odkazuje objekty** stromy pro vybranou položku.  
  
 ![Spravovaná halda stromu](../profiling/media/memuse__snapshotdetails_managedheaptree.png "MEMUSE__SnapshotDetails_ManagedHeapTree")  
  
|||  
|-|-|  
|**Typ objektu**|Název instance typu nebo objektu.|  
|**Počet**|Počet instancí objektů typu. Číslo je vždy 1 pro instanci.|  
|**Velikost (bajty)**|Pro typ, velikost všech instancí typu v paměti snímek, s výjimkou velikost objekty obsažené v instance.<br /><br /> Pro instance, typ, velikost objektu s výjimkou velikost objekty obsažené v instanci. instance.|  
|**(Včetně). velikost (bajty)**|Velikost instance typu nebo velikosti jediné instance, včetně velikosti obsažené objekty.|  
  
###  <a name="BKMK_Paths_to_Root_tree__Snapshot_details_"></a> Cesty do stromu kořenové (snímku podrobnosti)  
 **Cesty do stromu kořenové** ukazuje řetězec objektů, které odkazují na typ, nebo instance. Uvolňování paměti rozhraní .NET Framework vyčistí paměti pro objekt jenom v případě, že byly vydány všechny odkazy na ni.  
  
 ![Cesty, které se kořenový stromu pro typy](../profiling/media/memuse_snapshotdetails_type_pathstoroottree.png "MEMUSE_SnapshotDetails_Type_PathsToRootTree")  
  
 Při prohlížení typu v **cest k kořenové** stromu, počet typů, které obsahují odkazy na tento typ objektů, které se zobrazí v **počet odkazů** sloupce. Při analýze instance nezobrazí sloupec.  
  
###  <a name="BKMK_Referenced_Objects_tree__Snapshot_details_"></a> Odkazované objekty stromu (snímku podrobnosti)  
 **Odkazuje objekty** Strom zobrazuje objekty, které odkazuje na vybraný typ nebo instance.  
  
 ![Odkazovaná Objjects stromu pro instance](../profiling/media/memuse_snapshotdetails_referencedobjects_instance.png "MEMUSE_SnapshotDetails_ReferencedObjects_Instance")  
  
|||  
|-|-|  
|**Typ objektu / Instance**|Název instance typu nebo objektu.|  
|**Velikost (bajty)**|Pro typ, velikost všech instancích typu, s výjimkou velikost objekty obsažené v typu.<br /><br /> Pro instance, velikost objektu, s výjimkou velikost objekty obsažené v objektu.|  
|**(Včetně). velikost (bajty)**|Celková velikost instance typu nebo velikost instance, včetně velikosti obsažené objekty.|  
  
##  <a name="BKMK_Snapshot_difference__diff__reports"></a> Sestavy snímek rozdíl (rozdílové)  
 Snímek sestavy rozdíl (rozdílové) zobrazuje změny mezi primární snímku a jeho snímek, která byla provedena bezprostředně před. Otevřete sestavu rozdílů, vyberte jednu z odkazů v zobrazení snímku, jak je znázorněno na následujícím obrázku. Obě odkaz otevře stejné sestavě; jediným rozdílem je výchozí pořadí řazení **spravovaná halda** stromu v sestavě. Po sestava se otevře, můžete změnit pořadí řazení.  
  
 ![Odkazy na rozdíl sestavy v zobrazení snímku](../profiling/media/memuse_snapshotview_snapshotdifflinks.png "MEMUSE_SnapshotView_SnapshotDiffLinks")  
  
-   **MB** odkaz seřadí sestava podle **(včetně). velikost (bajty)** sloupce.  
  
-   **Objekty** odkaz seřadí sestava podle **počet** sloupce.  
  
###  <a name="BKMK_Managed_Heap_tree__Snapshot_diff_"></a> Spravovaná halda stromu (snímku rozdílové)  
 **Spravovaná halda** stromu jsou uvedeny typy objektů, které jsou uložené v paměti. Můžete rozbalit název typu zobrazíte deset největší instance typu, seřazené podle velikosti. Výběr typu nebo instance zobrazí **cest k kořenové** a **odkazuje objekty** stromy pro vybranou položku.  
  
 ![Spravovaná halda strom pro typu v sestavě rozdíl](../profiling/media/memuse_snapshotdiff_type_heap.png "MEMUSE_SnapshotDiff_Type_Heap")  
  
 Všimněte si, že **počet**, **velikost (bajty)**, a **(včetně). velikost (bajty)** sloupce mají byla sbalené na obrázku.  
  
|||  
|-|-|  
|**Typ objektu**|Název instance typu nebo objektu.|  
|**Počet**|Počet instancí typu v primární snímku. **Počet** je vždy 1 pro instanci.|  
|**Počet rozdílů**|Pro typ, počet instancí typu rozdíl mezi primární snímku a jeho předchozí snímek. Toto pole je prázdné, pokud instance.|  
|**Velikost (bajty)**|Velikost objektů v primární snímek, s výjimkou velikost objekty obsažené v objektech. Pro typ **velikost (bajty)** a **(včetně). velikost (bajty)** jsou součty velikostí instancí typu.|  
|**Diff celková velikost (bajty)**|Pro typ, celková velikost instance typu rozdíl mezi primární snímku a předchozího snímku, s výjimkou velikost objekty obsažené v instance. Toto pole je prázdné, pokud instance.|  
|**(Včetně). velikost (bajty)**|Velikost objektů v primární snímek, včetně velikosti objekty obsažené v objektech.|  
|**Diff (včetně). velikost (bajty)**|Pro typ, velikost všech instancí typu rozdíl mezi primární snímku a předchozího snímku, včetně velikosti objekty obsažené v objektech. Toto pole je prázdné, pokud instance.|  
  
###  <a name="BKMK_Paths_to_Root_tree__Snapshot_diff_"></a> Cesty do stromu kořenové (snímku rozdílové)  
 **Cesty do stromu kořenové** ukazuje řetězec objektů, které odkazují na typ, nebo instance. Uvolňování paměti rozhraní .NET Framework vyčistí paměti pro objekt jenom v případě, že byly vydány všechny odkazy na ni.  
  
 ![Cesty k kořenové strom pro instance v zobrazení rozdílů](../profiling/media/memuse_snapshotdiff_pathstoroot_instance_all.png "MEMUSE_SnapshotDiff_PathsToRoot_Instance_All")  
  
###  <a name="BKMK_Referenced_Objects_tree__Snapshot_diff_"></a> Odkazované objekty stromu (snímku rozdílové)  
 **Odkazuje objekty** Strom zobrazuje objekty, které odkazuje na typ primární, nebo instance.  
  
 ![Odkazovaná Objjects stromu pro instance](../profiling/media/memuse_snapshotdetails_referencedobjects_instance.png "MEMUSE_SnapshotDetails_ReferencedObjects_Instance")  
  
|||  
|-|-|  
|**Typ objektu / Instance**|Název instance typu nebo objektu.|  
|**Velikost (bajty)**|Pro instance, velikost objektu v primární snímek, s výjimkou velikost objekty obsažené v instanci.<br /><br /> Pro typ, celková velikost instance typu v primární snímek, s výjimkou velikost objekty obsažené v instanci.|  
|**(Včetně). velikost (bajty)**|Velikost objektů v primární snímek, včetně velikosti objekty obsažené v objektech.|  
  
## <a name="see-also"></a>Viz také  
 [Paměť jazyka JavaScript](../profiling/javascript-memory.md)  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)  
 [Osvědčené postupy z hlediska výkonu pro aplikace UWP pomocí C++, C# a Visual Basic](http://msdn.microsoft.com/library/windows/apps/hh750313.aspx)   
 [Diagnostika problémů paměti pomocí nástroje nové využití paměti v sadě Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=394706)