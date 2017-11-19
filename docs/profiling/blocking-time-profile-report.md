---
title: "Času blokace Sestava profilu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.report.blocking
helpviewer_keywords: Concurrency Visualizer, Blocking Time Profile Report
ms.assetid: 3bc45af0-3ba6-4fa3-a336-be8e9ae95107
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 199c33ce94aa1fcb5cffc45570a4425df3dbd720
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="blocking-time-profile-report"></a>Sestava profilu času blokace
Profil sestavy poskytují agregační blokování časových dat pro zásobníky volání, které jsou specifické pro jednotlivé blokování kategorie (například "Vstupně-výstupních operací" nebo "Synchronizace"). Sestava přerušování obsahuje seznam procesů, které zrušené aktuální proces společně se počet instancí přerušení. Pokud chcete vytvořit blokování Sestava profilu, nástroj shromažďuje blokování volání rozhraní API a shromáždí je do stromu zásobníky volání. Data zobrazená na tyto sestavy se liší podle aktuální časové rozmezí, skrytý vláken a následující dva filtry, které mohou být použity:  
  
-   Pokud je vybrána pouze můj kód, jsou uvedeny pouze rámce zásobníku, které mají uživatelského kódu, plus o jednu úroveň pod uživatelského kódu.  
  
-   Pokud je nastavena hodnota snížení šumu, kompletován zásobníky, které mají menší než zadaná četnost se přeskočí.  
  
 Rozbalte všechny položky volání stromu najít řádek kódu, ve kterém je blokování čas strávený. Vyhledejte řádek zdroje pro položku, na jeho místní nabídky, zvolte **zobrazit zdroj**. Vyhledejte řádek kódu, který volá tento jeden v místní nabídce zvolte **zobrazení volání webů**. Pokud jenom jedna lokalita volání je k dispozici, příkaz se připojí k zvýrazněný řádek kódu pro volání lokalitu. Pokud jsou k dispozici více volání weby, příkaz otevře dialogové okno, ve kterém můžete vybrat položku a pak zvolte **, přejděte na zdrojový** tlačítko zvýrazněná volání server vyhledejte. Často je velmi užitečné, chcete-li zobrazit zdrojový kód pro volání lokalitu, která obsahuje nejvíce instancí, nejvíce času nebo obojí.  
  
## <a name="blocking-time-report-columns"></a>Blokování sloupců čas sestavy  
 Následující tabulka zobrazuje sloupce pro všechny blokující čas sestavy.  
  
|Název sloupce|Popis|  
|-----------------|-----------------|  
|Název|Název funkce pro každou úroveň zásobníku volání.|  
|Instance|Počet instancí blokování volání pro viditelné časové období.|  
|Čas včetně blokování|Celkový počet blokování času stráveného pro všechny balíčky, které jsou shrnuty na této úrovni stromu zásobníku volání. Číslo (včetně) je součet hodnot výhradní blokování čas pro tuto funkci a výhradní blokování čas pro všechny jeho podřízené uzly.|  
|Výhradní blokování čas|Celkový počet blokování času stráveného při němž je tato funkce je nejnižší úroveň zásobníku volání. Položku zásobníku jedinečný volání, která má vysokou výhradní blokování čas může být funkce, které vás zajímají.|  
|Rozhraní API nebo počkejte kategorie|Zobrazit pouze pro funkce na nejnižší úrovni zásobníku volání. Pokud se podpis blokování volání rozpozná, je zadaný název blokování rozhraní API. Pokud není rozpoznán podpisu, který je hlášen jádra informace jsou poskytovány.|  
|Podrobnosti|Plně kvalifikovaný název funkce. To zahrnuje počet řádků, pokud je k dispozici.|  
  
### <a name="synchronization"></a>Synchronizace  
 Synchronizace sestava ukazuje volání, které jsou zodpovědní za segmentů, které blokují na synchronizaci a agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [čas synchronizace](../profiling/synchronization-time.md)  
  
### <a name="sleep"></a>Přejít do režimu spánku  
 Sestava režimu spánku zobrazí volání, které jsou zodpovědní za blokování dobu, po kterou byly připsány času stráveného v režimu spánku a agregační blokování doby každé zásobníku volání. Další informace najdete v tématu [doba režimu spánku](../profiling/sleep-time.md).  
  
### <a name="io"></a>I/O  
 Sestava vstupně-výstupních operací obsahuje volání, které jsou zodpovědní za segmentů, které blokují na vstupně-výstupních operací a agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [čas vstupně-výstupních operací (zobrazení vláken)](../profiling/i-o-time-threads-view.md).  
  
### <a name="memory-management"></a>Správa paměti  
 Správa paměti sestava ukazuje volání, které jsou zodpovědní za segmentů, které blokují na operace správy paměti a agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [čas správy paměti](../profiling/memory-management-time.md).  
  
### <a name="preemption"></a>Přerušování  
 Sestava přerušování obsahuje seznam procesů, které zrušené aktuální proces spolu s počtem instancí.  Můžete rozbalit jednotlivé procesy chcete zobrazit konkrétní vláken, která nahradí vláken v aktuálním procesu a chcete-li zobrazit rozpis instancí přerušení na vlákno. Tato sestava blokování je méně než ostatní možné použít, protože přerušování je obvykle vynucená pro váš proces operačního systému, nikoli k problému v kódu. Další informace najdete v tématu [čas přerušení](../profiling/preemption-time.md).  
  
### <a name="ui-processing"></a>Zpracování uživatelského rozhraní  
 Sestava zpracování uživatelského rozhraní obsahuje volání, které jsou zodpovědní za blokování segmentů, které blokují na bloky zpracování uživatelského rozhraní a agregace blokování časy každý zásobníku volání. Další informace najdete v tématu [doba zpracování uživatelského rozhraní](../profiling/ui-processing-time.md).  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)