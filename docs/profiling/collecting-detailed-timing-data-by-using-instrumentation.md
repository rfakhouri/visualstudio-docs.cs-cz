---
title: Shromažďování podrobných dat časování pomocí instrumentace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 11f16376ca9fe86dcb7d68cc7a0ca7e4f2d36db2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="collecting-detailed-timing-data-by-using-instrumentation"></a>Shromažďování podrobných dat časování pomocí instrumentace
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Metody instrumentace v nástrojích pro profilaci vloží profilování kód do kopie modulu. Kód zaznamenává každou položku, ukončení a volání funkce funkce v modulu během profilace spustit. Metoda instrumentace je užitečný při shromažďování časování podrobné informace o části kódu a porozumění vlivu vstupních a výstupních operací na výkon aplikace.  
  
 Metoda instrumentace můžete určit pomocí jedné z následujících postupů:  
  
-   Na první stránce průvodce profilace, vyberte **instrumentace**.  
  
-   Na **prohlížeč výkonu** panelu nástrojů v **metoda** seznamu, klikněte na tlačítko **instrumentace**.  
  
-   Na **Obecné** stránky dialogové okno Vlastnosti výkonnostní relace, vyberte **instrumentace**.  
  
## <a name="common-tasks"></a>Obecné úlohy  
 Můžete zadat další možnosti v *výkonnostní relace *** stránky vlastností** dialogové okno relace výkonu. Chcete-li otevřít toto dialogové okno:  
  
-   V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a pak klikněte na tlačítko **vlastnosti**.  
  
 Úkoly v následující tabulce popisují možnosti, které můžete zadat v *výkonnostní relace *** stránky vlastností** dialogové okno když profilu pomocí metody instrumentace.  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|Na **Obecné** přidat přidělení paměti .NET a životnosti a zadejte pojmenování podrobnosti vygenerovaný soubor profilování dat (.vsp).|-   [Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Na **spusťte** stránky, pokud máte více projektů .exe ve vaší solution.specify aplikace spustit a jejich pořadí spuštění.|-   [Postupy: určení binárního souboru spuštění](../profiling/how-to-specify-the-binary-to-start.md)|  
|Na **binární soubory** stránky, zadejte umístění pro instrumentovaného kopií modulů. Ve výchozím nastavení původní binární soubory přesunou do zálohovací složky.|-   [Postupy: přemístění instrumentovaných binárních souborů](../profiling/how-to-relocate-instrumented-binaries.md)|  
|Na **sledováním interakce vrstev** přidejte ADO.NET data volání do profilace spustit.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|  
|Na **instrumentace** stránky, vyloučit malé funkce z profilace ke snížení profilace režie, profil kódu jazyka JavaScript na webových stránkách ASP.NET a zadat příkazy, pomocí příkazového řádku před a po instrumentace proces.|-   [Postupy: vyloučení nebo zahrnutí funkce CShort z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Postupy: profilování kódu JavaScript ve webové stránky](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Postupy: Zadejte příkazy před a po instrumentaci](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|  
|Na **čítače CPU** stránky, zadejte jeden nebo více čítače výkonu procesoru pro přidání do data profilování.|-   [Postupy: shromažďování dat čítačů procesoru](../profiling/how-to-collect-cpu-counter-data.md)|  
|Na **události systému Windows** vyberte jeden nebo více událostí trasování událostí pro Windows (ETW) ke shromažďování dat vzorkování.|-   [Postupy: shromažďování trasování událostí pro Windows (ETW) dat](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Na **čítačů systému Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do data profilování jako značky.|-   [Postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Na **Upřesnit** zadejte jakékoli další možnosti, které chcete předat vsinstr – instrumentace programu, například možnosti, které chcete zahrnout nebo vyloučit konkrétní funkce.|-   [Postupy: určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Postupy: omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Vsinstr –](../profiling/vsinstr.md)|