---
title: Analýza využití paměti jazyka JavaScript v aplikacích pro UPW | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- JavaScript
helpviewer_keywords:
- dominators, memory analyzer (JavaScript)
- memory leaks (JavaScript)
- heap memory, JavaScript
- leaks, memory (JavaScript)
- snapshots, memory analyzer (JavaScript)
- JavaScript Memory Analyzer
- analyzing memory, JavaScript
- memory analyzer, JavaScript
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d064c1fdf5462a62b35b6d7902aaefc5cd409a8
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845649"
---
# <a name="analyze-javascript-memory-usage-in-uwp-apps"></a>Analýza využití paměti jazyka JavaScript v aplikacích pro UPW
Analyzátor paměti jazyka JavaScript je k dispozici v sadě Visual Studio vám pomohou pochopit, využití paměti a najít nevracení paměti v aplikace UWP vytvořená pro systém Windows pomocí jazyka JavaScript. Podporované aplikace patří aplikace pro univerzální aplikace pro Windows.
  
 Analyzátor paměti jazyka JavaScript může můžete provádět tyto akce:  
  
-   Můžete rychle najít paměti problémy využití ve vaší aplikaci pomocí zdůraznění nejdůležitější data.  
  
     Tato data zobrazí v souhrny snímků, které zobrazují rozdíly mezi dvěma snímky a nabízí odkazy na podrobnější zobrazení.  
  
-   Zadejte zobrazení dominantní objekty, typy a kořenových certifikačních autorit, které vám pomůžou izolovat problémy.  
  
-   Snižte není možné použít informace v datech haldy JavaScript.  
  
     Automaticky jsou vyfiltrovány objekty, které nejsou vytvořené přímo v kódu aplikace. Data můžete také filtrovat podle názvu objektu.  
  
## <a name="run-the-javascript-memory-analyzer"></a>Spustit Analyzátor paměti jazyka JavaScript  
 Analyzátor paměti můžete použít, když máte aplikaci UWP pracovní otevřete v sadě Visual Studio.
  
#### <a name="to-run-the-memory-analyzer"></a>Chcete-li spustit Analyzátor paměti  
  
1.  Otevřete Visual Studio.  
  
2.  Pokud spouštíte aplikaci ze sady Visual Studio v **spustit ladění** seznam na **standardní** nástrojů, vyberte cíl ladění pro projekt: buď **místního počítače** nebo **Zařízení**.  
  
3.  Na řádku nabídek zvolte **ladění**>**výkonu profileru**.  
  
     Ve výchozím nastavení se analyzují aktuální projekt po spuštění. Pokud chcete změnit cíl analýzy, zvolte **změnit cíl**.  
  
     ![Změna cílové analysis](../profiling/media/js_tools_target.png "JS_Tools_Target")  
  
     Jsou k dispozici pro cíl analysis následující možnosti:  
  
    -   **Spouštěný projekt**. Analyzuje aktuální projekt po spuštění. Pokud spouštíte aplikaci ve vzdáleném počítači, musíte zvolit tuto možnost, což je výchozí hodnota.  
  
    -   **Spuštění aplikace**. Umožňuje vybrat aplikaci UWP ze seznamu spuštěných aplikací. Tuto možnost nelze použít, když používáte aplikaci ve vzdáleném počítači.  
  
         Tuto možnost použijte k analýze využití paměti aplikací, které jsou spuštěné v počítači, pokud nemáte přístup ke zdrojovému kódu.  
  
    -   **Nainstalované aplikace**. Umožňuje vybrat nainstalovanou aplikaci UPW, který chcete analyzovat. Tuto možnost nelze použít, když používáte aplikaci ve vzdáleném počítači.  
  
         Tuto možnost použijte k analýze využití paměti aplikací, které jste nainstalovali v počítači, pokud nemáte přístup ke zdrojovému kódu. Tato možnost může být také užitečné, když chcete analyzovat využití paměti ve všech aplikací mimo váš vlastní vývoj aplikací.  
  
4.  Z **nástroje**, vyberte **paměť jazyka JavaScript** zaškrtněte políčko a zvolte **spustit**.  
  
5.  Při spuštění analyzátor paměti okno Řízení uživatelských účtů může požádat o oprávnění ke spuštění Collector.exe trasování událostí pro Windows Visual Studio. Zvolte **Ano**.  
  
     Komunikovat s aplikaci testovat scénáře použití relevantní paměti a zobrazit graf paměti, jak je popsáno v následujících částech.  
  
6.  Stisknutím kombinace přepnout do sady Visual Studio **Alt**+**kartě**.  
  
7.  Chcete-li zobrazit data, která je shromažďování analyzátor paměti, zvolte **trvat snímku haldy**. V tématu [zobrazit souhrn snímku](#SnapshotSummary) dál v tomto tématu.  
  
## <a name="check-memory-usage"></a>Zkontrolujte využití paměti  
 Můžete použít k identifikaci nevracení paměti pomocí různých zobrazení v analyzátor paměti jazyka JavaScript. Pokud již máte podezření, že vaše aplikace není vracena paměť, přečtěte si téma [izolovat nevrácená paměť systému](#Isolate) pro navrhovaná pracovního postupu.  
  
 Aby bylo možné identifikovat nevracení paměti v aplikaci použijte následující zobrazení:  
  
-   [Zobrazení souhrnu využití paměti za provozu](#LiveMemory). Graf využití paměti použijte k vyhledání nečekané zvýšení využití paměti nebo průběžně zvýšení využití paměti, která je výsledkem konkrétní akce. Souhrnné zobrazení využití paměti za provozu použijte k pořízení snímků haldě. Snímky se zobrazují jako kolekci v části grafu využití paměti.  
  
    > [!TIP]
    >  Zobrazí se špička využití paměti a při pořízení snímku. Použijte souhrny snímku pro přesnější údaj o růstu.  
  
-   [Zobrazit souhrn snímku](#SnapshotSummary). Můžete zobrazit souhrnné informace snímku během nebo po paměť relace profilování. Pomocí snímku souhrny propojit podrobnosti snímku a zobrazení rozdílů snímku.  
  
    > [!TIP]
    >  Zobrazení rozdílů snímku obvykle poskytne velmi užitečné informace o nevracení paměti.  
  
-   [Zobrazení podrobností snímku](#SnapshotDetails). Zobrazí podrobné data o využití paměti pro jeden snímek.  
  
-   [Zobrazit rozdílové snímku](#SnapshotDiff). Zobrazuje rozdílové hodnoty mezi snímky. Tato zobrazení zobrazit rozdíly v objektu velikost a objekt počty.  
  
## <a name="isolate-a-memory-leak"></a>Izolovat nevracení paměti  
 Tyto kroky obsahují pracovního postupu, které můžou pomoct efektivněji využívat analyzátor paměti jazyka JavaScript. Tyto kroky může být užitečné, pokud se domníváte, že má vaše aplikace nevrácenou pamětí. Kurz, který vás provede proces identifikace nevracení paměti v aplikaci pro práci, najdete v části [návod: Vyhledání nevrácené paměti (JavaScript)](../profiling/walkthrough-find-a-memory-leak-javascript.md).  
  
1.  Otevřete aplikaci v sadě Visual Studio.  
  
2.  Spusťte analyzátor paměti jazyka JavaScript. Další informace najdete v tématu [spustit Analyzátor paměti jazyka JavaScript](#Run).  
  
3.  Spuštění aplikace prostřednictvím scénář, který chcete testovat. Tento scénář například mohou zahrnovat velké mutace DOM, když konkrétní stránka načte, nebo při spuštění aplikace.  
  
4.  Opakujte tento scénář 1 – 4 další časy.  
  
    > [!TIP]
    >  Opakováním scénáře testu několikrát, můžete pomoct, ujistěte se, že pracovní inicializace je možné filtrovat mimo výsledky.  
  
5.  Přepnout na Visual Studio (stiskněte **Alt**+**kartě**).  
  
6.  Pořízení snímku haldy směrný plán tak, že zvolíte **trvat snímku haldy**.  
  
     Následující obrázek znázorňuje příklad snímku směrného plánu.  
  
     ![Základní snímku](../profiling/media/js_mem_leak_workflow_baseline.png "JS_Mem_Leak_Workflow_Baseline")  
  
    > [!TIP]
    >  Přesnější kontrolu nad načasování snímky, můžete použít [zdrojový kód přidružit data o využití paměti](#JSConsoleCommands) příkazů v kódu.  
  
7.  Přepněte do vaší aplikace a opakujte v situaci, že testujete (znovu pouze jednou).  
  
8.  Přepněte do sady Visual Studio a vytvořte druhý snímek.  
  
9. Přepněte do vaší aplikace a opakujte v situaci, že testujete (znovu pouze jednou).  
  
10. Přepněte do sady Visual Studio a vytvořte třetí snímek.  
  
     Následující obrázek znázorňuje příklad druhý a třetí snímku.  
  
     ![Druhý a třetí snímku](../profiling/media/js_mem_leak_workflow.png "JS_Mem_Leak_Workflow")  
  
     Provedením směrného plánu, druhý a třetí snímku v tomto pracovním postupu můžete filtrovat na změny, které nejsou přidruženy k nevracení paměti snadněji. Například může být očekávané změny jako aktualizace záhlaví a zápatí na stránce, která způsobí vygenerování některé změny využití paměti, ale mohou být vztah k nevracení paměti.  
  
11. Z třetí snímek vyberte odkaz na jedno z rozdílové zobrazení:  
  
    -   Velikost rozdílové haldy (levém odkaz pod velikost haldy). Text odkazu ukazuje rozdíl mezi velikost haldy aktuální snímek a velikost haldy předchozí snímek.  
  
    -   Počet objektů Differential (pravém odkaz pod počet objektů). Text odkazu se zobrazí dvě hodnoty (například +1858 /-1765): první hodnota je počet nových objektů přidaných od předchozího snímku, a druhá hodnota je počet objektů odebraných od předchozí snímek.  
  
     Tyto odkazy otevřete zobrazení podrobností rozdílové snímku typy v haldě seřadit zachované velikost nebo počet objektů, v závislosti na propojení, které jste otevřeli.  
  
12. Vyberte jednu z následujících **oboru** filtrování možností, aby bylo možné identifikovat problémy využití paměti:  
  
    -   **Objekty zbyly ze snímku č. 2**.  
  
    -   **Objekty přidané mezi snímku č. 2 a #3**  
  
    > [!TIP]
    >  Použití filtrovaných zobrazení objektů, které zbyly z předchozího snímku prozkoumat nevracení paměti. Například, pokud je počet rozdílové objektů +205 /-195, toto zobrazení zobrazí 10 objekty, které zbyly a toto jsou pravděpodobně kandidáti na nevracení paměti.  
  
     Následující obrázek znázorňuje rozdílové zobrazení objektů, které zbyly ze snímku č. 2.  
  
     ![Pořízení snímku rozdílové zobrazení typů](../profiling/media/js_mem_snapshot_diff.png "JS_Mem_Snapshot_Diff")  
  
     Na předchozím obrázku vidíte, že dva objekty byly ponechány z předchozího snímku. Zjistěte, zda se jedná o očekávané chování u konkrétní aplikace. Pokud ne, může to znamenat nevrácenou pamětí.  
  
13. Pokud chcete zobrazit, kde jsou objekty v zobrazení rozdílů root na globální objekt, který bude sdělovat, že se uvolňování paměti, otevřete místní nabídku pro objekt a zvolte **kořeny zobrazení**. Velký počet objektů, které může uchovávají v paměti, protože se odkazuje jeden objekt (nebo několik objektů), jsou root na globální objekt.  
  
14. Pokud jsou v zobrazení objektů, které zbyly příliš mnoho objektů, zkuste další izolovat období, ve kterém dochází k nevrácená paměť systému a potom retake tři snímky. Pokud chcete izolovat další nevrácená paměť systému, použijte [zdrojový kód přidružit data o využití paměti](#JSConsoleCommands), [zdrojový kód přidružit data o využití paměti](#JSConsoleCommands)a další data využití paměti v analyzátor paměti k dispozici.  
  
## <a name="view-live-memory-usage-summary"></a>Zobrazení souhrnu využití paměti za provozu  
 Souhrnné zobrazení využití paměti za provozu poskytuje graf využití paměti pro aplikace spuštěné a kolekce všechny dlaždice souhrnu snímku. V tomto zobrazení můžete provádět základní úlohy, jako je pořizování snímků, analýza souhrnné informace a přejdete k dalším zobrazením. Když zastavíte shromažďování dat, graf paměti vyčkat a zobrazí pouze [zobrazit souhrn snímku](#SnapshotSummary) zobrazení.  
  
 Paměť graf zobrazuje, za provozu zobrazení paměti procesu aplikace, která zahrnuje nesdílených bajtů, nativní paměti a haldě JavaScript. Graf paměti je posouvatelného zobrazení paměti procesu. Tady je bude vypadat takto:  
  
 ![Analyzátor paměti jazyka JavaScript paměti grafu](../profiling/media/js_mem_memory_graph.png "JS_Mem_Memory_Graph")  
  
 Pokud jste přidali uživatele značky do kódu aplikace (najdete v části [zdrojový kód přidružit data o využití paměti](#JSConsoleCommands)), inverzní trojúhelník se zobrazí v grafu využití paměti k označení, když je dosaženo této části kódu.  
  
 Některé z paměti zobrazený v grafu paměti je přidělena prostředí JavaScript runtime. Nelze řídit tento využití paměti v aplikaci. Využití paměti zobrazený v grafu zvyšuje při provádění první snímku a pak minimálně pro každý další snímku.  
  
## <a name="view-a-snapshot-summary"></a>Zobrazit souhrn snímku  
 Vytvořte snímek aktuálního stavu využití paměti vaší aplikace, zvolte **trvat snímku haldy** z paměti grafu. Souhrn dlaždici snímek, který se zobrazí v obou za provozu využití paměti souhrn (když aplikace běží) a Souhrn snímku (při zastavení je aplikace), poskytuje informace o haldy JavaScript a odkazy na podrobnější informace. Pokud pořídíte dvou nebo více snímků, snímek poskytuje další informace o porovnávání svá data, na který předchozí snímek.  
  
> [!NOTE]
>  Analyzátor paměti jazyka JavaScript vynutí uvolňování před jednotlivých snímků. To pomáhá zajistit konzistentní výsledky mezi spustí.  
  
 Tady je příklad snímku souhrn, kdy trvat několik snímků.  
  
 ![Souhrn snímku](../profiling/media/js_mem_snapshot_summary.png "JS_Mem_Snapshot_Summary")  
  
 Souhrn snímku zahrnuje:  
  
-   Název a časové razítko snímku.  
  
-   Počet potenciální problémy (označená ikonou blue informace). Toto číslo, pokud existuje, identifikuje potenciální problémy s pamětí například uzly, které nejsou připojené k modelu DOM. Počet odkazy na typy zobrazení snímek, který je seřazen podle typ problému, abyste měli na očích potenciální problémy. Popisek se zobrazí popis problému.  
  
-   Velikost haldy. Toto číslo zahrnuje elementů modelu DOM a objekty, které modul runtime jazyka JavaScript přidá k haldě JavaScript. Odkazy velikost haldy na typy zobrazení snímku.  
  
-   Velikost rozdílové haldy. Tato hodnota ukazuje rozdíl mezi velikost haldy aktuální snímek a velikost haldy předchozí snímek. Hodnota následuje červená, pokud je zvýšení paměti šipka nahoru nebo zelená šipka dolů Pokud dojde ke snížení paměti. Pokud velikost haldy nezměnila mezi snímky, zobrazí se text **žádná změna** místo číslo. Pro první snímek, zobrazí se text **směrného plánu**. Odkazy velikost rozdílové haldy na typy zobrazení rozdíl snímku  
  
-   Počet objektů. Tento počet zobrazí pouze objekty vytvořené v aplikaci a filtry předdefinované objekty vytvořené prostředí JavaScript runtime. Počet propojení objektů do typy zobrazení podrobností snímku.  
  
-   Počet rozdílové objektů. Ukazuje to dvou hodnot: první hodnota je počet nových objektů přidaných od předchozí snímek; a druhá hodnota je počet objektů odebraných od předchozí snímek. Například obrázek ukazuje, že byly přidány 1,859 objekty a 1,733 objekty byly odebrány od snímku č. 1. Tyto informace následuje red šipku, pokud má vyšší počet celkový počet objektů nebo zelená šipka dolů, pokud má zmenšit. Pokud se nezměnila počet objektů, zobrazí se text **žádná změna** místo číslo. Pro první snímek, zobrazí se text **směrného plánu**. Počet propojení rozdílové objektů do typy zobrazení rozdíl snímku  
  
-   Snímek obrazovky v době pořízení snímku.  
  
## <a name="view-snapshot-details"></a>Zobrazit podrobnosti o snímku  
 Podrobné informace o využití paměti pro každý snímek můžete zobrazit v zobrazení Podrobnosti o snímek.  
  
 Ze zobrazení souhrnu snímku kliknutím na odkaz zobrazíte detaily snímku. Například odkaz velikost haldy otevře snímek, který ve výchozím nastavení otevírat podrobnosti s typy zobrazení.  
  
 Tento obrázek ukazuje typy zobrazení podrobně snímku, s seřazené podle zachované velikost dat o využití paměti.  
  
 ![Potenciální potíže se zobrazuje zobrazení snímek podrobností](../profiling/media/js_mem_snapshot_details.png "JS_Mem_Snapshot_Details")  
  
 V zobrazení Podrobnosti o snímku můžete zkontrolovat data o využití paměti podle typu, root nebo dominator tak, že zvolíte možnost panelu nástrojů:  
  
-   **Typy**. Zobrazuje velikost instance počet a celkový počet objektů v haldě seskupené podle typu objektu. Ve výchozím nastavení ty jsou seřazené podle počtu instancí.  
  
    > [!TIP]
    >  Obvykle jsou rozdílové zobrazení typů v haldě objekt nejužitečnější zobrazení pro identifikaci nevrácená paměť systému; Tato zobrazení poskytují **oboru** filtr, aby bylo možné identifikovat doleva přes objekty.  
  
-   **Kořeny**. Zobrazí hierarchické zobrazení objektů z kořenové objekty prostřednictvím podřízené odkazy. Ve výchozím nastavení jsou podřízených uzlů seřazené podle sloupce zachované velikost, s největší v horní části.  
  
-   **Dominantní objekty**. Zobrazí seznam objektů v haldě, které mají výhradní odkazy na jiné objekty. Dominantní objekty jsou seřazené podle udržených velikost.  
  
    > [!TIP]
    >  Když odeberete dominator z paměti, můžete získat všechny paměť, který uchovává objekt. Na pár aplikací dominantní objekty zobrazení mohou pomoci vysvětlení velikostí zachované paměti, protože můžete prozkoumat řetězce odkazů kompletní objekt.  
  
 Všechny tři zobrazení zobrazit podobné typy hodnot, včetně:  
  
-   **Identifikátory**. Název, který nejlépe určuje objekt. Například pro elementy HTML snímků zobrazí podrobnosti hodnota atributu ID, pokud používá.  
  
-   **Typ**. Typ objektu (například prvek odkazu HTML nebo div element).  
  
-   **Velikost**. Velikost objektu není včetně velikosti všechny odkazované objekty.  
  
-   **Uchovávají velikost**. Velikost objektu plus velikost všechny podřízené objekty, které mají žádné jiné nadřazené položky. Pro účely praktické Toto je množství paměti zachována objekt, takže pokud odstraníte objekt uvolnění zadaného množství paměti.  
  
-   **Počet**. Počet instancí objektů. Tato hodnota se zobrazí pouze v zobrazení typů.  
  
## <a name="view-a-snapshot-diff"></a>Zobrazit rozdílové snímku  
 V analyzátor paměti jazyka JavaScript můžete porovnat snímek proti předchozí snímek v zobrazeních rozdílové snímku.  
  
 V zobrazení souhrnu snímku můžete zobrazit podrobnosti rozdílové snímku výběrem velikost haldy rozdílovou nebo rozdílovou objekt počet odkazů po dvou nebo více snímků nebyly provedeny.  
  
 Můžete zobrazit rozdílové informace o typech, kořeny a dominantní objekty. Diff snímku zobrazuje informace, jako jsou objekty, které byly přidány do haldy mezi dvěma snímky.  
  
 Tento obrázek ukazuje typy zobrazení v rozdíl snímku  
  
 ![Pořízení snímku rozdílové zobrazení typů](../profiling/media/js_mem_snapshot_diff.png "JS_Mem_Snapshot_Diff")  
  
 V okně rozdílové snímku zobrazení dominantní objekty, typy a kořenové adresáře jsou stejné jako v [zobrazit podrobnosti snímku](#SnapshotDetails) okno. Diff snímku zobrazuje stejné informace jako snímek podrobnosti, s následující hodnoty:  
  
-   **Velikost rozdílové**. Rozdíl mezi velikost objektu v aktuální snímek a jeho velikost v předchozí snímek, není včetně velikosti všech odkazovat objekty.  
  
-   **Velikost rozdílové uchovávají**. Rozdíl mezi udržených velikost objektu v aktuální snímek a jeho velikost zachované v předchozí snímek. Velikost udržených zahrnuje velikost objektu plus velikost všech jeho podřízených objektů, které mají žádné jiné nadřazené položky. Pro účely praktické zachované velikost je množství paměti zachována objekt, takže pokud odstraníte objekt uvolnění zadaného množství paměti.  
  
 Chcete-li filtrovat rozdílové informace mezi snímky, vyberte jednu z **oboru** filtrů v horní části rozdílové zobrazení.  
  
-   **Objekty zbyly ze snímku #\<číslo >**. Tento filtr zobrazuje rozdílů mezi objekty do haldy přidat nebo odebrat z haldy ve srovnání s snímku směrného plánu a předchozí snímek. Například, pokud se zobrazuje souhrn snímku +205 /-195 v počet objektů, tento filtr vám ukáže deset objekty, které byly přidány, ale neodeberou.  
  
    > [!TIP]
    >  Pokud chcete zobrazit velmi užitečné informace v tomto filtru, postupujte podle kroků popsaných v [izolovat nevrácená paměť systému](#Isolate).  
  
-   **Objekty přidané mezi snímku #\<číslo > a #\<číslo >**. Tento filtr obsahuje všechny objekty, které se přidají k haldě z předchozího snímku.  
  
-   **Všechny objekty v snímku #\<číslo >**. Toto nastavení filtru není filtrovat všechny objekty v haldě.  
  
 Zobrazíte odkazy na objekty, které neodpovídají aktuální **oboru** filtru, vyberte **zobrazit neodpovídající odkazy** v seznamu nastavení ![nastavení rozevírací&#45;dolů seznamu analyzátor paměti ] (../profiling/media/js_mem_settings.png "JS_Mem_Settings") v pravém horním rohu podokna. Pokud povolíte toto nastavení, zobrazí se neodpovídající odkazy s šedou barvou.  
  
> [!TIP]
>  Doporučujeme, postupujte podle kroků v [izolovat nevrácená paměť systému](#Isolate) a pak použijte objekty, které zbyly **oboru** filtr, aby bylo možné identifikovat objekty, které jsou vracena paměť.  
  
## <a name="view-objects-by-dominator"></a>Objekty zobrazení podle dominator  
 V zobrazení typů a dominantní objekty, můžete zvolit, zda chcete-li zobrazit objekty přeložen do jejich dominantní objekty (Toto je výchozí zobrazení v **dominantní objekty** karta). Pokud je vybráno toto zobrazení, v nejvyšší úrovně zobrazení objektů, které jsou uvedeny pouze dominantní objekty. (Objekty, které jsou následníky není globální objekty jsou skryta zobrazení nejvyšší úrovně.) Pro některé aplikace to vysvětlení objektů, které způsobují nevrácené paměti pomocí snížení šumu v datech.  
  
 Chcete-li přepnout zobrazení objektů tím dominator, zvolte **přeložte na objekty podle dominator** tlačítko. ![Skládání objekty do své dominantní objekty](../profiling/media/js_mem_fold_objects.png "JS_Mem_Fold_Objects")  
  
 Další informace o dominantní objekty, najdete v části [zobrazit podrobnosti snímku](#SnapshotDetails).  
  
## <a name="filter-data-by-identifier"></a>Filtrování dat podle identifikátoru  
 V zobrazení dominantní objekty a typy můžete filtrovat data vyhledáním konkrétní identifikátory. K vyhledání identifikátoru, stačí zadat jeho název v **identifikátor filtru** textového pole v pravém horním rohu. Když začnete psát, identifikátory, které neobsahují žádný zadané znaky jsou vyfiltrovány.  
  
 Každé zobrazení má vlastní filtr, takže filtru není zachová, i když přejdete do jiného zobrazení.  
  
## <a name="find-an-object-in-the-object-tree"></a>Vyhledání objektu ve stromu objektů  
 V zobrazení typů a dominantní objekty relace do konkrétní objekt uvidíte `Global` objektu. Objekty root k `Global` objekt nebude uvolňování paměti. Budete moci snadno najít objekt známé v zobrazení kořeny bez vyhledávání prostřednictvím `Global` stromu objektů. K tomu, otevřete v dominantní objekty místní nabídku pro objekt nebo typ zobrazení a potom vyberte **kořeny zobrazení**.  
  
## <a name="view-shared-object-references"></a>Zobrazovat odkazy na sdílené objekty  
 V zobrazení typů a dominantní objekty v dolním podokně obsahuje seznam odkazů na objekt zobrazující sdílený odkazy. Pokud v horním podokně vyberete objekt, zobrazí seznam objektů odkazy na všechny objekty, které odkazují na tento objekt.  
  
> [!NOTE]
>  Cyklické odkazy jsou uvedeny hvězdičkou (*) a informační popisek a nelze rozšířit. By se jinak, zabránit vám v proti nahoru k odkazu a identifikaci objektů, které jsou ponechá paměti.  
  
 Pokud chcete další nápovědu identifikace ekvivalentních objektů, vyberte **zobrazit identifikátory objektu** v seznamu nastavení ![nastavení rozevírací&#45;dolů seznamu analyzátor paměti](../profiling/media/js_mem_settings.png "JS_Mem_Settings ") v pravém horním rohu v horním podokně. Tato možnost zobrazí ID objektů vedle názvů objektů v **identifikátory** seznamu (ID se zobrazují ve všech zobrazeních, ne jenom odkazy na seznam objektů). Objekty, které mají stejné ID. jsou sdílené odkazy.  
  
 Následující obrázek znázorňuje seznamu objektů odkazy pro vybranou položku s ID zobrazí.  
  
 ![Odkazy s zobrazit identifikátory objektu](../profiling/media/js_mem_shared_refs.png "JS_Mem_Shared_Refs")  
  
## <a name="show-built-in-objects"></a>Předdefinované objekty zobrazení  
 Ve výchozím zobrazení dominantní objekty a typy zobrazit pouze objekty, které vytvoříte ve vaší aplikaci. Díky tomu můžete vyfiltrovat nepotřebné informace a izolovat problémy související s aplikací. Ale v některých případech může být užitečné pro zobrazení všech objektů, které generuje běhu programu JavaScript pro vaši aplikaci.  
  
 Pokud chcete zobrazit tyto objekty, zvolte **zobrazit built-ins** v seznamu nastavení ![nastavení rozevírací&#45;dolů seznamu analyzátor paměti](../profiling/media/js_mem_settings.png "JS_Mem_Settings") v pravém horním horním podokně.  
  
## <a name="save-diagnostic-session-files"></a>Uložte soubory relace diagnostiky  
 Diagnostické snímku souhrny a jejich přidružené podrobnosti zobrazení budou uloženy jako. *diagsession* soubory. **Průzkumník řešení** zobrazí předchozí relace diagnostiky ve složce diagnostiky relací. V **Průzkumníku**, otevřete předchozí relace, odebrat nebo přejmenovat soubory.  
  
## <a name="associate-source-code-with-memory-usage-data"></a>Zdrojový kód přidružit data o využití paměti  
 Snažte se určit části kódu, který má potíže paměti, použijte následující metody:  
  
-   Vyhledejte názvy tříd a identifikátory pro prvky DOM ve podrobnosti a rozdílové zobrazení.  
  
-   Vyhledejte řetězcové hodnoty v rozdílové zobrazení, které mohou být přidruženy vašeho zdrojového kódu a podrobnosti.  
  
-   Použití [vyhledání objektu ve stromu objektů](#ShowInRootsView) příkaz, který provede nahoru k objektu. To vám může pomoci identifikovat přidružené zdrojového kódu.  
  
-   Přidávání příkazů analyzátor paměti do vašeho zdrojového kódu.  
  
 Ve zdrojovém kódu, můžete použít následující příkazy:  
  
-   `console.takeHeapSnapshot` pořídí snímek haldy, který se zobrazí v analyzátor paměti jazyka JavaScript. Tento příkaz je jedním z [příkazy konzoly pro JavaScript](../debugger/javascript-console-commands.md).  
  
-   `performance.mark` Nastaví uživatele označit (inverzní trojúhelník), který se zobrazí v časovou osu grafu paměti v souhrnné zobrazení, když aplikace běží. Tento příkaz má jeden argument řetězec, který popisuje události a zobrazí se jako popisek v grafu paměti. Tento popis nesmí být delší než 100 znaků.  
  
> [!TIP]
>  Použití `console.takeHeapSnapshot` pro urychlení analýzy při opakování scénáře využití paměti.  
  
 Tyto příkazy vyvolána výjimka, pokud je přidejte do vaší aplikace a spuštění aplikace mimo analyzátor paměti jazyka JavaScript. Však můžete zkontrolovat, zda existují příkazy před jejich používání. (Příkazy neexistují již v rané fázi ve fázi spuštění relace.) Zkontrolujte, zda můžete bezpečně volat `takeHeapSnapshot`, použijte tento kód:  
  
```javascript  
if (console && console.takeHeapSnapshot) {  
    console.takeHeapSnapshot();  
}  
```  
  
 Zkontrolujte, zda můžete bezpečně volat `performance.mark`, použijte tento kód:  
  
```javascript  
if (performance && performance.mark) {  
    performance.mark("message_string");  
}  
  
```  
  
 Tady je graf paměti s několika značky uživatele a popis pro toto označení aktuálně vybraného uživatele, pro kterou `performance.mark` argument řetězce je nastaven na hodnotu "data generované":  
  
 ![Pomocí profilu označit](../profiling/media/js_mem_performance_marks.png "JS_Mem_Performance_Marks")  
  
## <a name="tips-to-identify-memory-issues"></a>Tipy k identifikaci problémů s pamětí  
  
-   Pracovní postup popsaný v [izolovat nevrácená paměť systému](#Isolate) a použít **objekty zbyly ze snímku #\<číslo >** filtru v zobrazení rozdílů k identifikaci pravděpodobně kandidáty na nevracení paměti.  
  
-   Použití [vyhledání objektu ve stromu objektů](#ShowInRootsView) zobrazíte, kde se objekt odkazuje v hierarchii paměti. Kořeny zobrazení ukazuje, jak se objekt zobrazuje na globální objekt, který by brání jeho uvolňování paměti.  
  
-   Pokud příčinu problému paměti je obtížné určit, použijte různých zobrazení (například dominantní objekty a typy) k vyhledání commonalities, zejména k identifikaci jeden objekt (nebo několik objektů), může obsahovat odkazy na řadu jiné objekty, které se zobrazují v zobrazení.  
  
-   Vyhledejte objekty, které jsou uchovány v paměti nechtěně po Uživatel přešel na novou stránku, což je obvyklou příčinou problémů s pamětí. Příklad:  
  
    -   Nesprávné použití [adresy URL. CreateObjectUrl](http://msdn.microsoft.com/library/windows/apps/hh453196.aspx) tento problém může být funkce.  
  
    -   Může poskytovat některé objekty `dispose` metoda a doporučení pro použití. Například by měly volat `dispose` na [WinJS.Binding.List](http://msdn.microsoft.com/library/windows/apps/Hh700774.aspx) při volání v seznamu `createFiltered` metoda a pak stránku opustit.  
  
    -   Možná budete muset odebrat jeden nebo více naslouchacích procesů událostí. Další informace najdete v tématu [naslouchacích procesů událostí DOM zobrazení](../debugger/view-dom-event-listeners.md).  
  
-   Podívejte se na část pozdější [toto video](http://channel9.msdn.com/Events/Build/2013/3-316) z konference Build 2013 o analyzátor paměti jazyka JavaScript.  
  
-   Čtení [správy paměti v aplikacích pro UPW](http://msdn.microsoft.com/magazine/jj651575.aspx).  
  
-   Zvažte, dočasně úpravu kódu izolovat problémy. Například můžete chtít:  
  
    -   Použijte příkazy pro analyzátor paměti `console.takeSnapshot` a `performance.mark`. (Viz [zdrojový kód přidružit data o využití paměti](#JSConsoleCommands).)  
  
         Můžete používat tyto příkazy lze izolovat problémy, které nelze izolovat ručně provedením haldy snímku.  
  
    -   Vytvořte objekt testu a trasování v zobrazeních analyzátor paměti jazyka JavaScript, jako jsou typy zobrazení. Například můžete připojit velký objekt k jinému objektu zobrazíte, zda určitý objekt nebo elementu byla uvolněna.  