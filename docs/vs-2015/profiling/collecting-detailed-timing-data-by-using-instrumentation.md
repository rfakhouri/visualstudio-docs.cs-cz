---
title: Shromažďování podrobných dat časování pomocí instrumentace | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c129ddf016e02fe6c29d5cf63fe57ba07fbd4e95
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60087973"
---
# <a name="collecting-detailed-timing-data-by-using-instrumentation"></a>Shromažďování podrobných dat časování pomocí instrumentace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Metody nástroje pro profilaci instrumentace vkládá kód profilování do kopie modulu. Kód zaznamenává každou položku, ukončení a volání funkce funkce v modulu během profilování. Metody instrumentace je užitečná pro shromažďování podrobných informací o časování o části kódu a k pochopení dopadu vstupních a výstupních operací na výkon aplikace.  
  
 Metoda instrumentace můžete zadat pomocí jedné z následujících postupů:  
  
- Na první stránce průvodce Profilováním, vyberte **instrumentace**.  
  
- Na **prohlížeč výkonu** nástrojů v **metoda** klikněte na možnost **instrumentace**.  
  
- Na **Obecné** stránky dialogové okno Vlastnosti relace výkonu, vyberte **instrumentace**.  
  
## <a name="common-tasks"></a>Obecné úlohy  
 Můžete zadat další možnosti v _relace výkonu_**stránky vlastností** dialogovému oknu relace výkonu. Chcete-li otevřít toto dialogové okno:  
  
- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na tlačítko **vlastnosti**.  
  
  Úkoly v následující tabulce popisují možnosti, které můžete určit _relace výkonu_**stránky vlastností** dialogové okno při profilování pomocí metody instrumentace.  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|Na **Obecné** stránce Přidat alokaci paměti .NET a data o životním cyklu a pojmenování detailů generovaného souboru dat profilování (.vsp).|-   [Shromažďuje alokaci paměti .NET a Data o životním cyklu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Na **spuštění** stránky, pokud máte více projektů .exe ve vaší solution.specify spuštění aplikace a jejich pořadí spouštění.|-   [Jak: Určení spouštěného binárního souboru](../profiling/how-to-specify-the-binary-to-start.md)|  
|Na **binární soubory** stránky, zadejte umístění pro instrumentované kopie modulů. Ve výchozím nastavení původní binární soubory přesunou do složky pro zálohy.|-   [Jak: Přemístění instrumentovaných binárních souborů](../profiling/how-to-relocate-instrumented-binaries.md)|  
|Na **interakce vrstev** stránce, přidejte data pro volání ADO.NET pro spuštění profilování.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|  
|Na **instrumentace** stránce, malé funkce vyloučit z profilace ke snížení profilace režie, profil kódu jazyka JavaScript na webových stránkách ASP.NET a zadat příkazy před a po spuštění z příkazového řádku proces instrumentace.|-   [Jak: Vyloučení krátkých funkcí z instrumentace nebo jejich zahrnutí do instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Jak: Profilování kódu JavaScript ve webových stránkách](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Jak: Zadání příkazů k provedení před instrumentací a po instrumentaci](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|  
|Na **čítače CPU** stránky, zadejte jeden nebo více čítačů výkonu procesoru pro přidání do profilových dat.|-   [Jak: Shromažďování dat čítačů procesoru](../profiling/how-to-collect-cpu-counter-data.md)|  
|Na **události Windows** vyberte jeden nebo více událostí trasování událostí pro Windows (ETW) pro shromažďování dat prostřednictvím data vzorkování.|-   [Jak: Shromažďování dat o trasování událostí pro Windows](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Na **čítače Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do profilových dat. jako značky.|-   [Jak: Shromažďování dat z čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Na **Upřesnit** stránky, zadejte jakékoli další možnosti, které chcete předat do programu VSInstr instrumentace, jako je například možnost zahrnout nebo vyloučit určité funkce.|-   [Jak: Zadání dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Jak: Omezení instrumentace na určité funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [VSInstr](../profiling/vsinstr.md)|
