---
title: Obecné vzory pro vícevláknové aplikace s nevhodným chováním | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.tools.gallery
helpviewer_keywords:
- Concurrency Visualizer, common patterns for poorly-behaved multithreaded applications
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4aec033266ccb2a6e6dcd0342669b7c31082488a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788853"
---
# <a name="common-patterns-for-poorly-behaved-multithreaded-applications"></a>Obecné vzory pro vícevláknové aplikace s nevhodným chováním

Vizualizátor souběžnosti pomáhá vývojářům k vizualizaci chování aplikace s více vlákny. Tento nástroj obsahuje galerii běžné vzory pro vícevláknové aplikace, které se chovají správně. Galerie obsahuje typický a rozpoznat visual vzory, které jsou vystaveny prostřednictvím nástroje, společně s vysvětlení chování, která je reprezentována každý vzorek, pravděpodobně výsledkem tohoto chování a nejběžnější přístup k jeho vyřešení.

## <a name="lock-contention-and-serialized-execution"></a>Kolize zámků a serializovaná spuštění

![Zamknout kolize, výsledkem je serializovaná provádění](../profiling/media/lockcontention_serialized.png "LockContention_Serialized")

Někdy aplikace paralelizované stubbornly pokračuje v provádění sériově i když má několik vláken a počítač nemá dostatečný počet logických jader. První symptomem je nízký s více vlákny výkon možná ještě o něco pomalejší než sériové provádění. V zobrazení vláken se nezobrazí více vláken, paralelním; spuštěním Místo toho uvidíte, že v každém okamžiku se provádí pouze jedno vlákno. Pokud kliknete na segment synchronizace ve vlákně, se v tomto okamžiku zobrazí zásobník volání pro vlákno blokované (blokovaný zásobník volání) a vlákna, které odebrat blokování podmínku (odblokování zásobníku volání). Kromě toho v případě odblokování zásobníku volání v procesu analýzy se zobrazí konektor připravený pro vlákno. Od této chvíle se můžete dostat do vašeho kódu z zásobníky volání blokování a odblokování zjistit příčinu serializace ještě více.

Jak je znázorněno na následujícím obrázku, Concurrency Visualizer můžete také zveřejnit tento příznak v zobrazení využití procesoru, kde, bez ohledu na přítomnost více vláken aplikace spotřebuje pouze jednoho logického jádra.

Další informace najdete v tématu "Start s oddílem problém" v článku MSDN Magazine [vlákna - prostředku kolize souběžnosti využívat profilaci výkonu v sadě Visual Studio 2010](https://msdn.microsoft.com/magazine/ff714587.aspx).

![Lock Contention](../profiling/media/lockcontention_2.png "LockContention_2")

## <a name="uneven-workload-distribution"></a>Rozdělení nerovnoměrné pracovního vytížení

![Nerovnoměrné úlohy](../profiling/media/unevenworkload_1.png "UnevenWorkLoad_1")

V případě nestandardní rozdělení práce mezi více paralelních vláken v aplikaci vzor typické střídavé kroku se zobrazí jako každý podproces dokončí svou práci, jak je znázorněno na předchozím obrázku. Vizualizátor souběžnosti zobrazí nejčastěji času velmi zavřít zahájení každé souběžné vlákno. Ale tato vlákna obvykle ukončit nesprávným způsobem místo koncové současně. Tento model určuje nestandardní rozdělení práce mezi skupinu paralelních vláken, které by mohlo vést k poklesu výkonu. Nejlepší metodou k těmto potížím se zpracovaly algoritmus, pomocí kterého byl rozdělen práce mezi paralelních vláken.

Jak je znázorněno na následujícím obrázku, Vizualizátor souběžnosti můžete také zveřejnit tento příznak v zobrazení využití procesoru jako postupná step-down využití výkonu procesoru.

![Nerovnoměrné úlohy](../profiling/media/unevenworkload_2.png "UnevenWorkload_2")

## <a name="oversubscription"></a>Překryvný odběr

![Překryvný odběr](../profiling/media/oversubscription.png "překryvného odběru")

V případě překročení stanovených počet aktivní vlákna v procesu je větší než počet logických jader dostupných v systému. Předchozí obrázek znázorňuje výsledky překryvného odběru s významné přerušování čáry v všechny aktivní vlákna. Kromě toho legendy ukazuje, že je velké procento času stráveného přerušení (v tomto příkladu 84 procent). To může znamenat, že proces požaduje spuštění více souběžných vláken, než je počet logických jader v systému. Nicméně to může také znamenat, že prostředky, které se předpokládá, že bude k dispozici pro tento proces používají jiné procesy v systému.

Při hodnocení tohoto problému byste měli zvážit následující:

- Může být oversubscribed celého systému. Zvažte, zda jiné procesy v systému může přerušený vlákna. Při přesunutí ukazatele myši přes segment přerušení v zobrazení vláken, popisek bude identifikovat vlákna a procesu přerušeno vlákno. Tento proces není nutně ten, který spouští po celou dobu procesu bylo přerušeno, ale ji poskytuje informace o co vytvořili přerušení tlak na váš proces.

- Vyhodnoťte, jak váš proces určuje odpovídající počet vláken pro spuštění v průběhu této fáze práce. Pokud váš proces přímo vypočítá počet aktivních podprocesů paralelní, zvažte úpravu algoritmu lepší počítat počet logických jader dostupných v systému. Pokud používáte modulu Runtime souběžnosti, Task Parallel Library a PLINQ, proveďte tyto knihovny práci při výpočtu počtu vláken.

## <a name="inefficient-io"></a>Neefektivní vstupně-výstupních operací

![Neefektivní můžu&#47;O](../profiling/media/inefficient_io.png "Inefficient_IO")

Nadměrné využití nebo zneužití vstupně-výstupních operací je běžnou příčinou nedostatků v aplikacích. Vezměte v úvahu na předchozím obrázku. Profil viditelné časové osy ukazuje, že 44 procent času viditelné vlákna je využívána vstupně-výstupních operací. Časová osa ukazuje velké množství vstupně-výstupních operací, což znamená, že profilované aplikace často neblokuje vstupně-výstupních operací. Chcete-li zobrazit podrobnosti o typech vstupně-výstupní operace a kde váš program je blokován, zvětšení problematických oblastí, zkontrolujte profil viditelné časové osy a klikněte na konkrétního bloku vstupně-výstupní operace zobrazíte aktuální zásobníky volání.

## <a name="lock-convoys"></a>Zámek sestavy

![Zamknout sestavy](../profiling/media/lock_convoys.png "Lock_Convoys")

Kdy aplikace získá zámky v pořadí první přijde, dřív, a rychlost přírůstku za na zámek je vyšší než počet pořízení dojde k uzamčení sestavy. Kombinace těchto dvou podmínek způsobí, že žádosti o zámek spusťte zálohování. Jedním ze způsobů boji proti tomuto problému je použít "nekalé" uzamčení nebo zámků, které poskytnout přístup k první vlákno je vyhledat v odemknout stavy. Toto chování konvoje. ten ukazuje předchozí obrázek. Chcete-li problém vyřešit, zkuste zmenšit kolizí pro synchronizaci objektů a zkuste použít nekalé zámky.

## <a name="see-also"></a>Viz také:

[Zobrazení vláken](../profiling/threads-view-parallel-performance.md)