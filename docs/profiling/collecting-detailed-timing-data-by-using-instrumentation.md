---
title: Shromažďování podrobných dat časování pomocí instrumentace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a58a5a1431dbb8ddbc9b23d93928f615e945b3b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62834304"
---
# <a name="collect-detailed-timing-data-by-using-instrumentation"></a>Shromažďování podrobných dat časování pomocí instrumentace
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Metody nástroje pro profilaci instrumentace vkládá kód profilování do kopie modulu. Kód zaznamenává každou položku, ukončení a volání funkce funkce v modulu během profilování. Metody instrumentace je užitečná pro shromažďování podrobných informací o časování o části kódu a k pochopení dopadu vstupních a výstupních operací na výkon aplikace.

 Metoda instrumentace můžete zadat pomocí jedné z následujících postupů:

- Na první stránce průvodce Profilováním, vyberte **instrumentace**.

- Na **prohlížeč výkonu** nástrojů v **metoda** klikněte na možnost **instrumentace**.

- Na **Obecné** stránky dialogové okno Vlastnosti relace výkonu, vyberte **instrumentace**.

## <a name="common-tasks"></a>Běžné úkoly
 Můžete zadat další možnosti v _relace výkonu_**stránky vlastností** dialogovému oknu relace výkonu. Chcete-li otevřít toto dialogové okno:

- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na tlačítko **vlastnosti**.

  Úkoly v následující tabulce popisují možnosti, které můžete určit _relace výkonu_**stránky vlastností** dialogové okno při profilování pomocí metody instrumentace.

|Úloha|Související obsah|
|----------|---------------------|
|Na **Obecné** stránce Přidat alokaci paměti .NET a data o životním cyklu a pojmenování detailů generovaného souboru dat profilování (.vsp).|-   [Shromažďování dat o přidělování a životnosti paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|
|Na **spuštění** stránky, pokud máte více projektů .exe ve vaší solution.specify spuštění aplikace a jejich pořadí spouštění.|-   [Jak: Určení binárního souboru ke spuštění](../profiling/how-to-specify-the-binary-to-start.md)|
|Na **binární soubory** stránky, zadejte umístění pro instrumentované kopie modulů. Ve výchozím nastavení původní binární soubory přesunou do složky pro zálohy.|-   [Jak: Přemístit instrumentované binární soubory](../profiling/how-to-relocate-instrumented-binaries.md)|
|Na **interakce vrstev** stránce, přidejte data pro volání ADO.NET pro spuštění profilování.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **instrumentace** stránce, malé funkce vyloučit z profilace ke snížení profilace režie, profil kódu jazyka JavaScript na webových stránkách ASP.NET a zadat příkazy před a po spuštění z příkazového řádku proces instrumentace.|-   [Jak: Vyloučení nebo zahrnutí krátkých funkcí z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Jak: Profilování kódu JavaScript ve webových stránkách](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Jak: Určení příkazů k provedení před instrumentací a po instrumentaci](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|
|Na **čítače CPU** stránky, zadejte jeden nebo více čítačů výkonu procesoru pro přidání do profilových dat.|-   [Postupy: shromažďování dat čítačů procesoru](../profiling/how-to-collect-cpu-counter-data.md)|
|Na **události Windows** vyberte jeden nebo více událostí trasování událostí pro Windows (ETW) pro shromažďování dat prostřednictvím data vzorkování.|-   [Jak: Shromažďování trasování událostí pro Windows (ETW) dat.](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|
|Na **čítače Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do profilových dat. jako značky.|-   [Jak: Shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|
|Na **Upřesnit** stránky, zadejte jakékoli další možnosti, které chcete předat do programu VSInstr instrumentace, jako je například možnost zahrnout nebo vyloučit určité funkce.|-   [Jak: Určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Jak: Omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [VSInstr](../profiling/vsinstr.md)|