---
title: Zobrazení podrobností funkce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.functiondetails
helpviewer_keywords:
- Function Details view
- Profiling Tools, Function Details view
ms.assetid: 8806954f-cf28-48d5-81b2-d722ceaf7d27
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7ce7bfbe9d68a7edcc0711c1f7e954612e67d0c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31578306"
---
# <a name="function-details-view"></a>Zobrazení podrobností funkce
**Zobrazení podrobností funkce** okně zobrazí následující informace:  
  
-   **Distribuce nákladů** vztahy mezi funkce, kterou jste vybrali a volání funkce, které provedeny vybrané funkce a mezi vybrané funkce a funkce, které byly volány představuje pruhový graf ho.  
  
-   **Podrobností výkonu funkce** tabulku, která zobrazuje souhrn profilování data pro funkce, která zadáte.  
  
-   **Zobrazení kódu funkce** okna, která zobrazuje funkce kódu, pokud kód je k dispozici.  
  
 **Zobrazení kódu funkce** okno je samostatný podokně. Ve výchozím nastavení, jsou dvě podokna Rozdělit vodorovně a **zobrazení kódu funkce** okno je umístěno v dolní části rámečku.  
  
-   Dvě podokna Rozdělit svisle, klikněte na tlačítko **rozdělení obrazovky svisle** na panelu nástrojů.  
  
-   Chcete-li změnit relativní velikost podoken, klikněte na šedé ohraničení mezi snímky a přetáhněte ohraničení do jiného umístění.  
  
## <a name="cost-distribution-bar-chart"></a>Náklady na distribuční pruhový graf  
  
### <a name="performance-metrics"></a>Metriky výkonu  
 V **metrika výkonu** rozevíracího seznamu můžete zadat hodnoty, které se v zobrazení. Hodnoty, které jsou k dispozici závisí na metodě profilování, který se používal v profilaci datového souboru. Názvy v závorkách jsou názvy řádků v **podrobností výkonu funkce** tabulky.  
  
### <a name="bar-chart"></a>Pruhový graf  
 **Volání funkcí**  
  
 **Volání funkce** panelu ukazuje funkce, které volá vybrané funkce. Velikost bloku, která obsahuje volání funkce je v poměru k příspěvku volání funkce na celkovou hodnotu metrika výkonu pro vybrané funkce.  
  
 Můžete kliknout na název volání funkce, aby bylo v zobrazení vybrané funkce.  
  
-   Pokud jsou moc volání funkcí seznam, funkce s nejnižší příspěvky se shromažďují v **jiných** bloku. Klikněte na tlačítko **jiných** zobrazíte všechny volající a volaná funkce vybrané funkce v **volající/volaný – zobrazení** okno. Další informace najdete v tématu [volající/volaný – zobrazení](../profiling/caller-callee-view.md).  
  
-   Pokud neexistují žádné volání funkcí, nebo pokud je funkce funkce položka vlákna nebo proces, **horní části zásobníku** bloku se zobrazí.  
  
 **Vybrané funkce**  
  
 Na panelu vybrané funkce zobrazí příspěvky volaných funkcí a kódu ve vybrané funkci metriky celkový výkon vybrané funkce. Velikost bloku, která obsahuje volané funkce nebo tělo funkce je poměr jeho příspěvku celkové hodnoty metriky výkonu pro vybrané funkce.  
  
 Můžete kliknout na název volané funkce, aby bylo v zobrazení vybrané funkce.  
  
-   **Celkový** hodnota je metrika výkonu pro vybrané funkce.  
  
-   **Tělo funkce** bloku představuje velikost celkové hodnoty metriky výkonu, které došlo v přímé provádění kódu v těle funkce.  
  
-   Funkce, které se nazývají vybrané funkce jsou uvedeny v blocích. Velikost bloku vybrané funkce představují množství celkový výkon Metrika pro vybrané funkce, která došlo k chybě v volaná funkce.  
  
-   Pokud jsou moc volání funkcí seznam, funkce s nejnižší příspěvky se shromažďují v **jiných** bloku. Klikněte na tlačítko **jiných** zobrazíte všechny volající a volaná funkce vybrané funkce v **volající/volaný – zobrazení** okno. Další informace najdete v tématu [volající/volaný – zobrazení](../profiling/caller-callee-view.md).  
  
-   Pokud neexistují žádné volaných funkcí **dolní zásobník** bloku se zobrazí.  
  
## <a name="function-performance-details"></a>Detaily výkonu funkce  
 Tabulky podrobností výkonu funkce poskytuje souhrnná data pro metriku výkonu vybrané funkce. Zobrazí se hodnota a procento. Zadejte zadejte profilování data, která se zobrazí v grafu a podrobnosti tabulky v **metrika výkonu** seznamu.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Exkluzivní**|-Množství metriku výkonu, došlo k chybě při provádění tělo funkce.|  
|**Ve volání**|-Množství metriku výkonu, došlo k chybě ve funkcích, které vybrané funkce volána.|  
|**Celkový počet (včetně).**|-Celkem **výhradní** a **volání v** hodnoty.|  
  
## <a name="function-code-view"></a>Zobrazení kódu – funkce  
 **Zobrazení kódu funkce** okno zobrazí seznam ve zdrojovém kódu, jakmile bude k dispozici. Vedle řádky kódu zdroje, které volat další funkce šedou barvou sloupec obsahuje hodnoty metriky výkonu pro volaná funkce. Chcete-li upravit zdrojový kód, klikněte na odkaz k souboru zdrojového kódu.  
  
## <a name="cost-distribution-bar-chart-values"></a>Hodnoty grafu panelu distribuční náklady  
  
### <a name="sampling"></a>Vzorkování  
 Následující tabulka vysvětluje hodnoty v seznamu metrika výkonu pro profilaci data, která nebyla shromážděna pomocí metody vzorkování.  
  
|||  
|-|-|  
|**Včetně ukázky (shromážděných ukázky)**|-Pro volání funkce, počet vzorků, které byly shromážděny při vybrané funkce byla zavolána pomocí této funkce volání.<br />-Pro tělo funkce, počet vzorků, které byly shromážděny při provádění vlastní kód vybrané funkce.<br />-Pro vyvolání funkce, počet vzorků, které byly shromážděny při byla volaná funkce provádění z důvodu volání z vybrané funkce.|  
  
### <a name="instrumentation"></a>Instrumentace  
 Následující tabulka vysvětluje hodnoty v seznamu metrika výkonu pro profilaci data, která nebyla shromážděna pomocí metody instrumentace.  
  
|||  
|-|-|  
|**Uplynulá doba včetně (uplynulý čas)**|Uplynulý čas zahrnuje času stráveného v volání operačního systému, jako jsou přepínače kontextu a vstupně výstupní operace.<br /><br /> -Pro **volání funkce**, množství času, po který byl potřebná k provedení instancí vybrané funkce, které byly volá funkci. Čas strávený v funkce volané vybrané funkce je zahrnuta.<br />-Pro **tělo funkce**, celkovou velikost uplynulá doba potřebná k provedení kód vybrané funkce. Čas strávený v volaná funkce není součástí.<br />-Pro volaná funkce velikost doba potřebná k provedení instancí funkce, které byly volány vybrané funkce. Celkový počet zahrnuje času stráveného v funkce, které funkce volána. Čas strávený v funkce volané vybrané funkce je zahrnuta.|  
|**Aplikace včetně čas (Time aplikace)**|Doba aplikace nezahrnuje času stráveného v volání operačního systému, jako jsou přepínače kontextu a vstupně výstupní operace.<br /><br /> -Pro **volání funkce**, množství času aplikace, která byla potřebná k provedení instancí vybrané funkce, které byly volá funkci. Čas strávený v funkce volané vybrané funkce je zahrnuta.<br />-Pro **tělo funkce**, celkovou dobu provádění aplikace potřebná k provedení kód vybrané funkce. Čas strávený v volaná funkce není součástí.<br />-Pro volaná funkce velikost aplikace doba potřebná k provedení instancí funkce, které byly volány vybrané funkce. Celkový počet zahrnuje času stráveného v funkce, které funkce volána.|  
  
### <a name="net-memory"></a>Využívání paměti rozhraním .NET  
 Následující tabulka vysvětluje hodnoty v seznamu metrika výkonu pro profilaci data, která nebyla shromážděna pomocí metody profilace paměti .NET.  
  
|||  
|-|-|  
|**Včetně přidělení (přidělení)**|-Pro **volání funkce**, počet objektů, které byly přiděleny instancemi vybrané funkce, která je volána funkce. Počet zahrnuje objekty, které byly přiděleny podle funkce, které vybrané funkce volána.<br />-Pro **tělo funkce**, počet objektů, které byly přiděleny podle vybrané funkce při provádělo vlastní kód. Přidělené v funkce volá funkci vybrané objekty nejsou zahrnuty.<br />-Pro vyvolání funkce počet objektů, které byly přiděleny instancemi funkce, které byly volány vybrané funkce. Počet zahrnuje objekty, které byly přiděleny podle funkce, které funkce volána.|  
|**Včetně bajtů (bajty)**|-Pro **volání funkce**, počet bajtů, které byly přiděleny instancemi vybrané funkce, která je volána funkce. Obsahuje počet bajtů, které byly přiděleny podle funkce, které vybrané funkce volána.<br />-Pro **tělo funkce**, celkový počet bajtů, které byly přiděleny podle vybrané funkce, když se při spouštění vlastní kód. Bajtů přidělených v funkce volané vybrané funkce nejsou zahrnuty.<br />-Pro vyvolání funkce počet bajtů, které byly přiděleny instancemi funkce, které byly volány vybrané funkce. Obsahuje počet bajtů, které byly přiděleny podle funkce, které volá funkci.|  
  
### <a name="concurrency"></a>Souběžnost  
 Následující tabulka vysvětluje hodnoty v seznamu metrika výkonu pro profilaci data, která nebyla shromážděna pomocí metoda souběžného zpracování.  
  
|||  
|-|-|  
|**Včetně kolizí (kolizí)**|-Pro **volání funkce**, počet prostředků kolizní události, k nimž došlo v instance vybrané funkce, která je volána funkce. Počet zahrnuje kolizní události ve funkcích, které vybrané funkce volána.<br />-Pro **tělo funkce**, celkový počet kolizní události, které došlo k chybě při provádění vlastní kód funkce. Kolizí, ke kterým dochází v funkce, které byly volány vybrané funkce nejsou zahrnuty.<br />-Pro vyvolání funkce počet kolizní události, k nimž došlo v instancí funkce, které byly volány vybrané funkce. Počet zahrnuje kolizní události, k nimž došlo v funkce, které funkce volána.|  
|**Včetně blokované čas (Time blokovaných)**|-Pro volání funkce času stráveného v prostředku kolizí, že události pro instance vybrané funkce, která bude volána funkce. Čas zahrnuje blokované čas ve funkcích, které vybrali volaná funkce.<br />-Pro **tělo funkce**, celková doba strávená v kolizní události, které došlo k chybě při provádění vlastní kód funkce. Kolizí, ke kterým dochází v funkce, které bude volána vybrané funkce nejsou zahrnuty.<br />-Pro vyvolání funkce času stráveného v prostředku kolizní události pro instance funkce, která bude volána vybrané funkce. Čas zahrnuje blokované dobu, po kterou došlo k chybě v funkce, které funkce volána.|