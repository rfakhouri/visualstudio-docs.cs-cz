---
title: Zobrazení volající / volaný – Data instrumentace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Caller/Callee view
ms.assetid: 0908d354-aa5c-4518-8631-e25b8e7649e5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c1970c8a026e509cb31a9a58a0ae42777425bef
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54945278"
---
# <a name="callercallee-view---instrumentation-data"></a>Zobrazení volající/volaný – data instrumentace
Zobrazení volající/volaný zobrazí profilování informace o vybrané funkce a její nadřazené a podřízené funkce ve stromu volání. Zobrazení volající/volaný obsahuje tři mřížky.  
  
 **Aktuální funkce** se zobrazí v mřížce střední který ukazuje profilování informace o vybrané funkce. Hodnoty zahrnují všechna volání funkce.  
  
 **Funkce, které volaly aktuální funkcí** se zobrazí v hlavní mřížky který ukazuje profilování informace o funkcích volající (nadřazené) z vybrané funkce. Hodnoty označuje množství hodnotu aktuální funkci, která byla vygenerována volání z této funkce volajícího.  
  
 **Funkce, které byly volány aktuální funkcí** se zobrazí v mřížce dolů který ukazuje profilování informace o instancích sady volaný (podřízený) funkce vybrané funkce. Hodnoty označit jenom při spuštění, který byl vynaložen ve funkci podřízený, když byla volána aktuální funkce.  
  
## <a name="general"></a>Obecné  
 Obecné sloupce rozpoznat funkci zobrazení řádku.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název funkce**|Název funkce.|  
|**Adresa funkce**|Adresa funkce.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Počet volání**|Celkový počet volání této funkce.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje funkci.|  
|**ID procesu**|ID procesu (PID) běhu profilování.|  
|**Název procesu**|Název procesu.|  
|**Výhradní čas režie**|Časová náročnost této funkce, která způsobila instrumentace. Režie byla odečtena od vylučuje všechny časy.|  
|**Celkový čas režie**|Časová náročnost této funkce a její podřízené funkce, která způsobila instrumentace. Test zatížení byla odečtena od fiskálního (včetně).|  
|**Typ**|Kontext funkce:<br /><br /> **0** -aktuální funkce<br /><br /> **1** – funkce, která volá aktuální funkci<br /><br /> **2** – funkce, která volá aktuální funkci<br /><br /> Pouze v [VSPerfReport](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
|**Název kořenové funkce**|Název aktuální funkce. Pouze v [VSPerfReport](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
  
## <a name="elapsed-inclusive-values"></a>Uplynulý včetně hodnoty  
 Uplynulý včetně hodnoty označuje datum a čas, který funkce byla v zásobníku volání. Čas zahrnuje, čas, který byl stráven v podřízené funkce a čas, který byl stráven voláními do operačního systému, například vstupně výstupní operace a přepnutí kontextu.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Uplynulý celkový čas**|-Pro aktuální funkci čas, který byl vynaložen ve funkci. Hodnota zahrnuje čas, který byl stráven v podřízené funkce a volání do operačního systému, jako je například vstupně výstupní operace a přepnutí kontextu.<br />-Pro volající funkce množství uplynulý celkový čas aktuální funkci, která byla vygenerována volání z této funkce volajícího.<br />-Pro volaných funkce čas, který byl stráven v instancích této funkce, které byly vytvořeny voláním z aktuální funkce. Hodnota zahrnuje čas, který byl stráven v podřízené funkce volaný a ve volání do operačního systému, například vstupně výstupní operace a přepnutí kontextu.|  
|**% Uplynulého celkového času**|Procento celkového uplynulý celkový čas, který byl stráven v uplynulý celkový čas této funkce v tomto kontextu spuštění profilování.|  
|**Průměrný uplynulý celkový čas**|Průměr uplynulý celkový čas volání této funkce v tomto kontextu.|  
|**Maximální uplynulý celkový čas**|Maximální uplynulý celkový čas volání této funkce v tomto kontextu.|  
|**Minimální uplynulý celkový čas**|Minimální uplynulý celkový čas volání této funkce v tomto kontextu.|  
  
## <a name="elapsed-exclusive-values"></a>Uplynulý výhradní hodnoty  
 Uplynulý výhradní hodnoty označuje datum a čas, který funkce byla spuštěna přímo v horní části zásobníku volání. Čas zahrnuje čas, který byl stráven ve volání do operačního systému, jako jsou přepínače kontextu a vstupně výstupní operace, ale nezahrnuje čas, který byl stráven v podřízené funkce.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Uplynulý výhradní čas**|-Pro aktuální funkci čas, který se využilo na přímé provádění funkce. Hodnota zahrnuje čas, který byl stráven v podřízené funkce a volání do operačního systému, jako je například vstupně výstupní operace a přepnutí kontextu.<br />-Pro volající funkce množství uplynulý výhradní čas aktuální funkci, která byla vygenerována volání z této funkce volajícího.<br />-Pro volaných funkce čas, který byl stráven v instancích této funkce, které byly vytvořeny voláním z aktuální funkce. Hodnota nezahrnuje čas, který byl stráven v podřízené funkcí volaných funkcí, ale obsahuje volání do operačního systému, jako je například vstupně výstupní operace a přepnutí kontextu.|  
|**% Uplynulého výhradního času**|Procento celkového uplynulý výhradní čas, který běhu profilování se využilo na celkový uplynulý výhradní čas této funkce v tomto kontextu.|  
|**Průměrný uplynulý výhradní čas**|Průměr uplynulý výhradní čas volání této funkce v tomto kontextu.|  
|**Maximální uplynulý výhradní čas**|Maximální uplynulý výhradní čas volání této funkce v tomto kontextu.|  
|**Minimální uplynulý výhradní čas**|Minimální uplynulý výhradní čas volání této funkce v tomto kontextu.|  
  
## <a name="application-inclusive-values"></a>Aplikace (včetně) hodnot  
 Aplikace (včetně) hodnot označuje datum a čas, který funkce byla v zásobníku volání. Čas nezahrnuje čas, který byl stráven ve volání do operačního systému, jako jsou přepínače kontextu a vstupně výstupní operace, ale neobsahuje čas, který byl stráven v podřízené funkce.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Celkový čas aplikace**|-Pro aktuální funkci čas, který se využilo na funkci a její podřízené funkce. Hodnota nezahrnuje čas, který byl stráven voláními do operačního systému, například vstupně výstupní operace a přepnutí kontextu.<br />-Pro volající funkce množství celkový čas aplikace aktuální funkce, která byla vygenerována volání z této funkce volajícího.<br />-Pro volaných funkce čas, který byl stráven v instancích této funkce, které byly vytvořeny voláním z aktuální funkce. Tato hodnota zahrnuje čas, který byl stráven v podřízené funkcí volaných funkcí, ale nezahrnuje čas, který byl stráven ve volání do operačního systému, například vstupně výstupní operace a přepnutí kontextu.|  
|**% Celkového času aplikace**|Procento celkového uplynulý celkový čas, který běhu profilování se využilo na celkový čas celkový aplikace této funkce v tomto kontextu.|  
|**Průměrný celkový čas aplikace**|Celkový čas průměrná aplikace volání této funkce v tomto kontextu.|  
|**Maximální celkový čas aplikace**|Celkový čas aplikace maximální volání této funkce v tomto kontextu.|  
|**Minimální celkový čas aplikace**|Celkový čas aplikace minimální volání této funkce v tomto kontextu.|  
  
## <a name="application-exclusive-values"></a>Výhradní hodnoty aplikace  
 Výhradní hodnoty, které aplikaci určit čas, který byl vynaložen ve funkci. To nezahrnuje čas, který se využilo na podřízené funkce a také nezahrnuje volání do operačního systému, jako je například vstupně výstupní operace a přepnutí kontextu.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní čas aplikace**|-Pro aktuální funkci čas, který se využilo na přímé provádění funkce. Hodnota nezahrnuje čas, který byl stráven v podřízené funkce ani obsahuje volání do operačního systému, jako je například vstupně výstupní operace a přepnutí kontextu.<br />-Pro volající funkce množství výhradní čas aplikace aktuální funkce, která byla vygenerována volání z této funkce volajícího.<br />-Pro volaných funkce čas, který byl stráven v instancích této funkce, které byly vytvořeny voláním z aktuální funkce. Hodnota nezahrnuje čas, který byl stráven v podřízené funkcí volaných funkcí ani obsahuje volání do operačního systému, jako je například vstupně výstupní operace a přepnutí kontextu.|  
|**% Výhradního času aplikace**|Procento celkového uplynulý výhradní čas, který běhu profilování se využilo na výhradní čas aplikace celkový této funkce v tomto kontextu.|  
|**Průměrný výhradní čas aplikace**|Výhradní čas aplikace průměrné volání této funkce v tomto kontextu.|  
|**Maximální výhradní čas aplikace**|Výhradní čas aplikace maximální volání této funkce v tomto kontextu.|  
|**Minimální výhradní čas aplikace**|Výhradní čas aplikace minimální volání této funkce v tomto kontextu.|  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení volající/volaný – vzorkování dat](../profiling/caller-callee-view-sampling-data.md)   
 [Zobrazení volající/volaný – data vzorkování paměti .NET](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Zobrazení volající/volaný – data instrumentace paměti .NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)