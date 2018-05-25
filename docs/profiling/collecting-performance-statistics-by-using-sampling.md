---
title: Shromažďování statistik výkonu pomocí vzorkování | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,sampling
- sampling profiling method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fef6883056affd6ee47da86d8f2860c8c9ca047
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
---
# <a name="collect-performance-statistics-by-using-sampling"></a>Shromažďování statistik výkonu pomocí vzorkování

Ve výchozím nastavení shromažďuje metody vzorkování profilace nástroje sady Visual Studio profilování informace každých 10 000 000 cyklů procesoru (přibližně každých jedné setině sekundu v počítači 1 GHz). Metoda vzorkování je užitečné pro hledání problémy s využitím procesoru a je navržené způsob spuštění většina vyšetřování výkonu.

> [!NOTE]
> Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

Metoda vzorkování můžete určit pomocí jedné z následujících postupů:

- Na první stránce průvodce profilace, klikněte na tlačítko **vzorkování procesoru (doporučeno)**.
- Na **prohlížeč výkonu** panelu nástrojů v **metoda** seznamu, klikněte na tlačítko **vzorkování**.
- Na **Obecné** stránky dialogovém okně Vlastnosti výkonnostní relace klikněte na tlačítko **vzorkování**.

## <a name="common-tasks"></a>Běžné úlohy

Můžete zadat další možnosti v *výkonnostní relace *** stránky vlastností** dialogové okno relace výkonu. Chcete-li otevřít toto dialogové okno:

- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a pak klikněte na tlačítko **vlastnosti**.

 Úkoly v následující tabulce popisují možnosti, které můžete zadat v *výkonnostní relace *** stránky vlastností** dialogové okno když profilu pomocí metody vzorkování.

|Úloha|Související obsah|
|----------|---------------------|
|Na **Obecné** přidat přidělení paměti .NET a shromažďování dat životnost a zadejte pojmenování podrobnosti vygenerovaný soubor profilování dat (.vsp).|- [Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />- [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|
|Na **vzorkování** stránky, změna míry vzorkování, změňte událostí vzorkování z hodinových cyklů procesoru na jiného počítadla výkonu procesoru nebo obě změnit...|- [Postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)|
|Na **spusťte** zadejte aplikaci spustit a spusťte pořadí, pokud máte více .exe projekty v řešení kódu.|- [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **sledováním interakce vrstev** přidejte informace o volání ADO.NET na data shromažďovaná v theprofiling spustit.|- [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **události systému Windows** zadejte jeden nebo více událostí trasování událostí pro Windows (ETW) ke shromažďování dat vzorkování.|- [Postupy: shromažďování trasování událostí pro Windows (ETW) dat](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|
|Na **čítačů systému Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do data profilování jako značky.|- [Postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|
|Na **Upřesnit** určete verzi modulu runtime rozhraní .NET Framework profilu, pokud vaše aplikace moduly pomocí více verzí. Ve výchozím nastavení je první verze načíst profilovaným.|- [Postupy: Zadejte modul Runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|