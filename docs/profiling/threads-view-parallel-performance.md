---
title: "Vláken (paralelní výkon) zobrazení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.threadblocking
helpviewer_keywords: Concurrency Visualizer, Threads View (Parallel Performance)
ms.assetid: 2e441103-a266-407b-88c3-fb58716257a3
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bdad50eff09e96c5d9c0513be1f571a901278871
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="threads-view-parallel-performance"></a>Zobrazení vláken (paralelní výkon)
Zobrazení vláken je nejvíce podrobnější a bohaté funkce zobrazení v vizualizér souběžnosti. Pomocí tohoto zobrazení, můžete zjistit, jestli jsou vláken provádění nebo blokování z důvodu synchronizace, vstupně-výstupních operací nebo z jiného důvodu.  
  
 Vizualizér souběžnosti během analýzy profil prověří všechny události přepnutí kontextu operačního systému pro každou aplikaci přístup z více vláken. Kontext přepínače může dojít z mnoha důvodů, například tyto:  
  
-   Vlákno je na primitivní synchronizace zablokovaný.  
  
-   Platnost vyprší quantum vlákna.  
  
-   Vlákno požádá blokování vstupně-výstupní operace.  
  
 Zobrazení vláken přiřadí kategorii každý přepínač kontext po zastavení provádění vlákna. Kategorie se zobrazí v legendě v levém dolním část zobrazení. Vizualizér souběžnosti řadí přepnutí kontextu události do kategorií vyhledáním zásobníku volání vlákna dobře známé blokování rozhraní API. Pokud neexistuje shoda zásobníku volání, z důvodu čekání, které poskytuje [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] se používá. Ale [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] kategorie může být založeno na podrobností implementace a nemusí odrážet záměr uživatele. Například [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] sestavy čekání důvod pro blokování zámku nativní tenký čtení a zápis jako vstupně-výstupních operací místo synchronizace. Ve většině případů můžete identifikovat hlavní příčinu blokování událostí tak, že prověří zásobníky volání, které odpovídají přepnutí kontextu události.  
  
 Zobrazení vláken také ukazuje závislosti mezi vlákny. Například pokud identifikovat podproces, který je blokovaný na synchronizační objekt, můžete vyhledat vlákno, které ho odblokováno a aktivity v zásobníku volání pro toto vlákno v bodě můžete zkontrolovat, když ho odblokováno jiný.  
  
 Při provádění jsou vláken, shromažďuje vizualizér souběžnosti ukázky. V zobrazení vláken můžete analyzovat, který kód spuštěný jeden nebo více podprocesů během segment provádění. Můžete také zkontrolovat blokování sestavy a sestavy, které profilu spuštění stromu zásobníku volání.  
  
## <a name="usage"></a>Použití  
 Zde jsou některé způsoby, které můžete zobrazení vláken:  
  
-   Identifikujte důvodů, proč je reagovat uživatelské rozhraní (UI) aplikace během určité fáze spouštění.  
  
-   Určete množství času, který strávil blokování synchronizace, vstupně-výstupních operací, chyb stránek a dalších událostí.  
  
-   Určete míru narušení z další procesy, které jsou prováděny v systému.  
  
-   Identifikujte problémy Vyrovnávání zatížení pro paralelní zpracování.  
  
-   Identifikujte důvody pro škálovatelnost, která je zhoršené nebo neexistující (například proto výkon paralelní aplikace se nezvyšuje, když jsou k dispozici více logických jader).  
  
-   Pochopení stupeň souběžnosti v aplikaci, která vám pomůžou paralelizace.  
  
-   Pochopení závislosti mezi pracovních vláken a kritické cesty provádění.  
  
## <a name="examining-specific-time-intervals-and-threads"></a>Zkoumání vláken a specifické časové intervaly  
 Zobrazení vláken zobrazuje časové osy. Můžete přiblížení a posouvání v rámci časovou osu pro zjištění určitých intervalech a vláken vaší aplikace. Na ose x je čas a na ose y jsou několik kanály:  
  
-   Pro každou jednotku disku na systém, jeden kanál pro čtení a jeden pro zápisy dva kanály vstupně-výstupní operace.  
  
-   Kanál pro každé vlákno v procesu.  
  
-   Kanály značky, pokud jsou značky události v trasování. Značky kanály původně vyskytovat v části přístup z více vláken kanály, které vygeneruje tyto události.  
  
-   Grafický procesor kanály.  
  
 Tady je ilustraci zobrazení vláken:  
  
 ![Zobrazení vláken](../profiling/media/threadsviewnarrowing.png "ThreadsViewNarrowing")  
Zobrazení vláken  
  
 Na začátku posloupnosti jsou řazeny v pořadí, ve kterém jsou vytvořeny, tak, aby se první hlavní vlákno aplikace. Možnost řazení v levém horním rohu zobrazení můžete použít k seřazení vláken podle jiného kritéria (například ve většině provádění práce).  
  
 Můžete skrýt, vláken, které nejsou provede práci výběrem jejich názvy ve sloupci na levé straně a pak klepnutím **skrýt vybrané vláken** tlačítka na panelu nástrojů. Doporučujeme, abyste skrýt vláken, které jsou zcela zablokovány, protože jejich statistiky jsou důležité a můžete clog sestavy.  
  
 K identifikaci další vlákna ke skrytí v aktivní legenda, vyberte **souhrnu podle vláken** sestavy **Sestava profilu** kartě. Zobrazí se provádění rozpis grafu, který se zobrazuje stav vláken pro aktuálně vybrané časový interval. Na úrovních některé přiblížení nemusí být zobrazeny některé vláken. V takovém případě se zobrazí symbol tří teček vpravo.  
  
 Pokud jste vybrali intervalu dobu a některé vláken v něm, můžete začít analýzy výkonu.  
  
## <a name="analysis-tools"></a>Nástrojů pro analýzu  
 Tato část popisuje, sestavy a jiných nástrojů pro analýzu.  
  
### <a name="thread-blocking-details"></a>Podrobnosti o blokování přístup z více vláken  
 Chcete-li získat informace o blokování událostí v určité oblasti na vlákno, ukazatele myši na danou oblast zobrazíte popisek. Pokud je obsahuje informace, například kategorie, čas spuštění oblast, blokování doba trvání a blokování rozhraní API. Pokud vyberete blokování oblasti, zobrazí se v dolním podokně, společně s stejné informace, které se zobrazí v popisu tlačítka zásobníku v tomto bodě v čase. Prověřením zásobníku volání, můžete určit základní důvod pro blokování vláken událost. Výběrem segmentu a zkoumání aktuální karta můžete najít další proces a informace o přístup z více vláken.  
  
 Cesta provádění může mít více blokování událostí. Můžete zkontrolovat tak, že blokování kategorie, aby mohli najít problémových oblastí rychleji. Právě v legendě na levé straně vyberte jednu z blokování kategorií.  
  
### <a name="dependencies-between-threads"></a>Závislosti mezi vlákny  
 Vizualizér souběžnosti můžete zobrazit závislosti mezi vlákny v procesu, aby mohla určit, co blokované vlákno pokusil provést a zjistěte, jaké jiné vlákno povoleno ji provést. Pokud chcete zjistit, které vlákno odblokováno jiné vlákno, vyberte příslušné blokování segmentu. Pokud vizualizér souběžnosti můžete určit odblokování vlákno, nakreslí čáru mezi odblokování vlákno a provádění segment, který následuje blokování segmentu. Kromě toho **Unblocking zásobníku** kartě se zobrazují v zásobníku volání relevantní.  
  
### <a name="thread-execution-details"></a>Podrobnosti o vlákně provádění  
 V časová osa grafu vlákna zelená segmenty zobrazit, když ho provádění kódu. Můžete získat podrobnější informace o segment provádění.  
  
 Když vyberete bod v segment provádění, vizualizér souběžnosti hledá tento bod v čase v zásobníku volání relevantní a potom zobrazí černé šipka nahoru výše k vybranému bodu v segmentu provádění a zásobníku volání sám sebe na  **Aktuální zásobníku** kartě. Můžete vybrat více bodů v provádění segmentu.  
  
> [!NOTE]
>  Vizualizér souběžnosti nemusí být schopni vyřešit výběr v provádění segmentu. Obvykle k tomu dochází, pokud je doba trvání segmentu méně než jeden milisekundu.  
  
 Chcete-li získat profilem spuštění pro všechny povolené (zobrazí) vláken v aktuálně vybrané časové rozmezí, zvolte **provádění** tlačítka na aktivní Legenda.  
  
### <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu zobrazí aktivitu všechna vlákna v procesu a všechna zařízení fyzického disku na hostitelském počítači. Zobrazí také GPU aktivity a značky události.  Chcete-li zobrazit více podrobností nebo mimo zobrazení delší časové období se můžete přiblížit. Můžete také vybrat body na graf pro získání podrobností o kategorie, časy zahájení, doby trvání a stavy zásobníku volání.  
  
 V tomto grafu časová osa barvu, která označuje stav vlákna v daném okamžiku. Například měla provádění zelená segmenty, red segmenty byly blokovaný pro synchronizaci, byly zrušené žlutý segmentů a fialové segmenty byly zapojený do zařízení vstupně-výstupní operace. Toto zobrazení můžete zkontrolovat zůstatek pracovní mezi vláken, které se podílejí v paralelní smyčky nebo souběžné úlohy. Pokud trvá delší dobu než jiné vlákno, může nevyváženou práci. Tyto informace slouží k distribuci pracovní více rovnoměrně mezi vláken vylepšit výkon vašeho programu.  
  
 Pokud pouze jedno vlákno je zelený (provádění) v bodě v čase, aplikace nemusí být plně využít souběžnost v systému. Časová osa grafu můžete zkontrolovat závislosti mezi vláken a dočasné vztahy mezi blokování a zablokuje vláken. Ke změně uspořádání vláken, vyberte vlákna a na panelu nástrojů vyberte nahoru nebo dolů tlačítko. Chcete-li skrýt vláken, vyberte je a potom vyberte **skrýt vláken** tlačítko.  
  
### <a name="profile-reports"></a>Profilu, sestavy  
 Pod časovou osu grafu je profil časové osy a podokno, které jsou karty pro různé sestavy. Sestavy automaticky aktualizuje, když změníte zobrazení vláken. Pro velké trasování může být podokně sestav není k dispozici při jsou vypočítávány aktualizace. Každá sestava obsahuje dvě úpravy filtru: noise snížení a pouze můj kód. Pomocí snížení šumu vyfiltrovat položky stromu volání, kde je málo čas strávený. Výchozí hodnota filtru je % 2, ale můžete jej přizpůsobit v rozsahu 0 až 99 procent. Chcete-li zobrazit pouze stromu volání kódu, vyberte **pouze můj kód** zaškrtávací políčko. Chcete-li zobrazit všechny volání stromy, zrušte jeho zaškrtnutí.  
  
#### <a name="profile-report"></a>Sestava profilu  
 Tato karta zobrazuje sestavy, které odpovídají položky v legendě active. Chcete-li zobrazit sestavu, zvolte jeden ze záznamů.  
  
#### <a name="current-stack"></a>Aktuální zásobníku  
 Na této kartě se zobrazuje zásobníku volání pro vybraný bod v segment přístup z více vláken v časová osa grafu. Zásobníky volání jsou oříznut zobrazíte pouze aktivity, která souvisí s vaším programem.  
  
#### <a name="unblocking-stack"></a>Odblokování zásobníku  
 V tématu, které vlákno odblokováno vybrané vlákno, a v jaké řádek kódu, vyberte **Unblocking zásobníku** kartě.  
  
#### <a name="execution"></a>Spuštění  
 Provádění sestava ukazuje rozdělení času stráveného aplikace při provádění.  
  
 Najít řádek kódu, ve kterém je provádění čas strávený, rozbalte strom volání a zvolte na místní nabídku pro položku volání stromu, **zobrazit zdroj** nebo **zobrazení volání webů**. **Zobrazit zdroj** vyhledá spuštěného řádku kódu. **Zobrazení volání lokalit** vyhledá řádek kódu, který volá spuštěného řádku kódu. Pokud jenom jedna lokalita volání existuje, je označený jeho řádek kódu. Pokud existuje více lokalit volání, můžete si vybrat ten, který chcete v dialogu, který se zobrazí a potom zvolte **, přejděte na zdrojový** tlačítko zvýrazněte kód lokality volání. Často je velmi užitečné najít lokalitu volání, která obsahuje nejvíce instancí, nejvíce času nebo obojí. Další informace najdete v tématu [Sestava profilu spuštění](../profiling/execution-profile-report.md).  
  
#### <a name="synchronization"></a>Synchronizace  
 Synchronizace sestava ukazuje volání, které jsou zodpovědní za synchronizaci bloky, společně s agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [čas synchronizace](../profiling/synchronization-time.md).  
  
#### <a name="io"></a>I/O  
 Sestava vstupně-výstupních operací obsahuje volání, které jsou zodpovědní za bloky vstupně-výstupních operací, společně s agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [čas vstupně-výstupních operací (zobrazení vláken)](../profiling/i-o-time-threads-view.md).  
  
#### <a name="sleep"></a>Přejít do režimu spánku  
 Sestava režimu spánku zobrazí volání, které jsou zodpovědní za bloky režimu spánku, společně s agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [doba režimu spánku](../profiling/sleep-time.md).  
  
#### <a name="memory-management"></a>Správa paměti  
 Sestava správy paměti obsahuje volání, kde bloky správy paměti došlo k chybě, společně s agregace blokování časy každý zásobníku volání. Tyto informace můžete určit oblasti, které mají nadměrné stránkování nebo paměti kolekce problémy.  Další informace najdete v tématu [čas správy paměti](../profiling/memory-management-time.md).  
  
#### <a name="preemption"></a>Přerušování  
 Tato sestava přerušování zobrazuje instance, kde procesy v systému zrušené aktuálním procesem a jednotlivých vláken, která nahradí vláken v aktuálním procesu. Tyto informace můžete použít k identifikaci procesy a vláken, které nejvíce odpovídají za přerušení. Další informace najdete v tématu [čas přerušení](../profiling/preemption-time.md).  
  
#### <a name="ui-processing"></a>Zpracování uživatelského rozhraní  
 Sestava zpracování uživatelského rozhraní obsahuje volání, které jsou zodpovědní za uživatelského rozhraní, zpracování bloky, společně s agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [doba zpracování uživatelského rozhraní](../profiling/ui-processing-time.md).  
  
#### <a name="per-thread-summary"></a>Za souhrn přístup z více vláken  
 Na této kartě zobrazuje zobrazení barevně sloupec celkový čas, každé vlákno věnovaný spustit, blokované, vstupně-výstupních operací a ostatní stavy. Sloupce, které jsou označené dole. Při změně úrovně přiblížení v časová osa grafu na této kartě se automaticky aktualizuje. Na úrovních některé přiblížení nemusí být zobrazeny některé vláken. V takovém případě se zobrazí symbol tří teček vpravo. Pokud vlákno, které chcete nezobrazí, můžete skrýt, jiná vlákna. Další informace najdete v tématu [za přístup z více vláken souhrnnou sestavu](../profiling/per-thread-summary-report.md).  
  
#### <a name="disk-operations"></a>Diskových operací  
 Tato karta zobrazuje které procesy a vláken byly součástí diskové vstupně-výstupních operací jménem aktuální proces, které soubory se dotýkal (například knihovny DLL, které byly načteny), kolik bajtů byly čtení a další informace. Tato sestava slouží k vyhodnocení času stráveného v přístupu k souborům během provádění, zejména v případě, že je váš proces je pravděpodobně vázán vstupně-výstupní operace. Další informace najdete v tématu [sestava diskových operací](../profiling/disk-operations-report-threads-view.md).  
  
## <a name="see-also"></a>Viz také  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)