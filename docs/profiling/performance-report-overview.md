---
title: Přehled sestavy výkonu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, about performance rerports
- performance, reports
- performance reports, about performance reports
ms.assetid: 7324c24c-fd09-479b-b2ad-e0c3b613e040
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af31d6bce4f1c44fbe759423ddaeec9537054688
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255990"
---
# <a name="performance-report-overview"></a>Přehled sestavy výkonu
Můžete zobrazit data profilování výkonu relace v **Sestava výkonu** okno Visual Studio Team System vývoj Edition integrované vývojové prostředí (IDE). Data profilování je uložen v .vsp a .vsps soubory. Zobrazení sestav systému windows umožňují zobrazit a analyzovat problémy s výkonem aplikace.  
  
> [!CAUTION]
>  Profilování datový soubor obsahuje citlivé informace, jako je název počítače, verze operačního systému, cesty k souborům, informace o paměti a další informace o instalaci počítače. Je vhodné ponechat přísnou kontrolu distribuci dat, v jeho nativní. *vsp* formátu a když se exportují do. *CSV* nebo. *XML* souboru.  
>   
>  Pokud jako součást výkonnostní relace se shromažďují data události trasování, další informace se může objevit události protokolu trasování (. *ETL*) souboru. Tyto informace zahrnují doména a uživatelské jméno; Proto je vhodné ponechat přísnou kontrolu rozdělení souboru protokolu.  
  
## <a name="performance-report-window"></a>Okno Sestava výkonu  
 Sestava výkonu není nástroj okně, který slouží k zobrazení, spravovat a filtrovat údaje o výkonu a obsahuje ovládací prvek přizpůsobitelné dotazu.  
  
 Na hlavním panelu nástrojů okna sestavy výkon můžete přístup každý zobrazení. Klikněte na šipku vedle položky **aktuální zobrazení** seznamu můžete zobrazit a vybrat jednotlivé zobrazení, které jsou k dispozici.  
  
 Okno Sestava výkonu najdete následující zobrazení, data:  
  
### <a name="summary-view"></a>Souhrnné zobrazení  
 Ve výchozím nastavení se profilace data zobrazí v souhrnné zobrazení. Toto zobrazení je výchozím bodem při šetření do problémy s výkonem. Z každého řádku v souhrnné zobrazení byste přejít na podrobnější zobrazení kliknutím pravým tlačítkem na název funkce nebo modul. Další informace najdete v tématu [zobrazení souhrnu](../profiling/summary-view.md).  
  
### <a name="callercallee-view"></a>Volající/volaný – zobrazení  
 Zobrazení volající/volaný zobrazí strom volání pro jednotlivé funkce. Zobrazení je rozdělené do tří částí:  
  
-   Funkce cíl se zobrazí uprostřed zobrazení.  
  
-   Funkce, které volal funkci (volající) se zobrazí nad funkce cíl.  
  
-   Funkce, které se nazývají funkcí cíl (volané) se zobrazí pod cíl.  
  
 Dvojitým kliknutím na libovolnou funkci v seznamu názvem nebo volaný seznamu můžete vybrat jiné funkce. Další informace najdete v tématu [volající/volaný – zobrazení](../profiling/caller-callee-view.md).  
  
### <a name="call-tree-view"></a>Zobrazení stromu volání  
 Zobrazení stromu volání zobrazuje cesty provádění funkce, které byly provázán v PROFILOVANÉHO aplikaci. Kořen stromu je vstupním bodem do aplikací nebo součástí. Každý uzel funkce uvádí všechny funkce, které ji volat a údaje o výkonu o těchto volání funkcí.  
  
 Zobrazení stromu volání můžete také rozšířit a zvýraznit cestu spuštění funkce, která nejvíce času spotřebovaného nebo byl vzorkovat nejčastěji. Zobrazení Nejaktivnější cesty, klikněte pravým tlačítkem na funkci a pak klikněte na **rozbalte aktivní trase**. Další informace najdete v tématu [zobrazení stromu volání](../profiling/call-tree-view.md).  
  
### <a name="process-view"></a>Zobrazení procesů  
 Proces zobrazení ukazuje údaje o výkonu pro každý proces a podproces, který byl vytvořený profil. Další informace najdete v tématu [zobrazení procesů](../profiling/process-view.md).  
  
### <a name="modules-view"></a>Zobrazení modulů  
 Zobrazení modulů seznam modulů v projektu a uvede data profilování pro každý modul. Rozbalit nebo sbalit na název modulu pro zobrazení funkce profilace data. Pokud data nebyla shromážděna pomocí vzorkování, řádku a instrukce ukazatele na zdrojový kód profilace dat se také k dispozici. Další informace najdete v tématu [moduly zobrazení](../profiling/modules-view.md).  
  
### <a name="functions-view"></a>Zobrazení funkcí  
 Zobrazení funkcí jsou uvedené funkce, které byly během profilace volat. Další informace najdete v tématu [zobrazení funkcí](../profiling/functions-view.md).  
  
### <a name="line-view"></a>Řádky – zobrazení  
 Zobrazení řádků umožňuje zobrazit řádky kódu konkrétního zdroje, které byly provedeny během profilace se vzorkováním. Další informace najdete v tématu [zobrazení řádků](../profiling/lines-view.md).  
  
### <a name="instruction-pointer-ip-view"></a>Instrukce ukazatele (IP) – zobrazení  
 Ukazatel instrukce zobrazení umožňuje zobrazit konkrétní pokyny, které byly provedeny během profilace vzorkování. Další informace najdete v tématu [zobrazení ukazatele na instrukce (IP)](../profiling/instruction-pointers-ips-view.md).  
  
### <a name="allocation-view"></a>Přidělení – zobrazení  
 Je k dispozici zobrazení přidělení Pokud **shromažďovat .NET objekt přidělení** byl vybrán na **Obecné** stránky **výkonnostní relace** dialogové okno Vlastnosti. V tématu [přehled výkonnostní relace](../profiling/performance-session-overview.md). Zobrazení přidělení uvádí objekty rozhraní .NET, které byly přiděleny pomocí aplikací nebo součástí. Po rozšíření řádku k objektu, se zobrazí strom volání. Volání Strom zobrazuje provádění cesty, jejichž výsledkem vytvoření objektu. Informace se zobrazí také o počtu (včetně) a výhradní přidělení pro jednotlivé funkce ve stromové struktuře volání. Zobrazení přidělení můžete také rozbalte a zvýraznit cestu spuštění funkce, která přidělené největší počet objektů. Zobrazení Nejaktivnější cesty, klikněte pravým tlačítkem na funkci a pak klikněte na **rozbalte aktivní trase**. Další informace najdete v tématu [data přidělení a dobu života paměti .NET shromažďovat](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md) a [přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md).  
  
### <a name="objects-lifetime-view"></a>Zobrazení doby života objektů  
 Doba života objektu zobrazení je k dispozici Pokud **.NET shromažďování informací o přidělení objektu** a **taky shromažďovat informace o doba života objektu .NET** nebyly vybrány na **Obecné**stránky **výkonnostní relace** dialogové okno Vlastnosti.  
  
 Doba života objektu zobrazení zobrazí celkový počet instancí každý typ a počet objektů, které byly shromážděny v každé kolekci generace uvolňování paměti. Další informace najdete v tématu [zobrazení doby života objektu](../profiling/object-lifetime-view.md).  
  
## <a name="customizable-filter-control"></a>Ovládání přizpůsobitelné filtru  
 Ovládací prvek přizpůsobitelné filtru obsahuje následující možnosti:  
  
-   **Filtr pro import** -načte dříve uloženou vlastní dotaz.  
  
-   **Export filtru** -uloží vlastní dotaz do zadaného umístění.  
  
-   **Spuštění dotazu** -spustí dotaz podle zobrazení v ovládacím prvku vlastního dotazu.  
  
-   **Zastavit dotazu** -zastaví provádění dotazu, který běží. Toto tlačítko není k dispozici, pokud je spuštěný žádný dotaz.  
  
-   **Zobrazit dotaz** -zobrazí nebo skryje ovládacího prvku vlastního dotazu.  
  
-   **Uložit Analyzed** -uloží sestavu společně s jeho aktuální analysis jako soubor .vsps.  
  
-   **Export** -uloží aktuální sestavu v. Formátovaný CVS nebo. Soubor ve formátu XML, pomocí možnosti k uložení různá zobrazení.  
  
## <a name="see-also"></a>Viz také:  
 [Analýza dat nástrojů výkonu](../profiling/analyzing-performance-tools-data.md)   
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)