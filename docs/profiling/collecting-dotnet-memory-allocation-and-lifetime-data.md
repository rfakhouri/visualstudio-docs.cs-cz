---
title: Shromažďování dat životnost a přidělení paměti .NET | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools,.NET memory method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 7e8c63316cc4ca13f74e1b66b2346cf329465e0c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34548632"
---
# <a name="collect-net-memory-allocation-and-lifetime-data"></a>Shromažďování dat o alokaci paměti a době platnosti objektů .NET

Profilace nástroje sady Visual Studio podporují kolekci přidělení paměti .NET a dat doba platnosti objektů, které vám pomůže zjistit problémy s výkonem souvisejících s pamětí ve vaší aplikaci.

- Data o přidělení paměti .NET zahrnuje velikost a počet objektů paměti rozhraní .NET Framework, které byly přiděleny.

- Životnosti objektů zahrnuje velikost a počet objektů paměti rozhraní .NET Framework, získaných v tři generace kolekce paměti.

> [!NOTE]
> Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

Data můžete shromáždit pomocí vzorkuje nebo metoda profilování instrumentace.

- Při použití metody vzorkování profileru sleduje všechny přidělení paměti .NET a objekty, které jsou generovány nástrojem proces, který byl spuštěn, nebo připojený k.

- Při použití metody instrumentace profileru sleduje pouze přidělení paměti .NET a objekty, které jsou generované instrumentovaného moduly.

> [!IMPORTANT]
> Při shromažďování dat paměti .NET (přidělení, životnosti objektu nebo obojí) pomocí metody vzorkování, jsou ignorovány všechny zadané uživatelem vzorkování události a události přidělení odpovídající paměti se používá ke shromažďování dat.

Pokud povolíte profilování přidělení paměti of.NET, je také povolit zobrazení přidělení. Pokud povolíte profilace rozhraní .NET životnosti, můžete také povolit zobrazení doby života objektů. Další informace najdete v tématu [přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md) a [zobrazení doby života objektu](../profiling/object-lifetime-view.md).

Informace o tom, jak shromažďování dat paměti .NET pomocí nástroje příkazového řádku nástrojích pro profilaci najdete v tématu pomocí metod rozhraní .NET paměti k přidělení paměti shromažďovat a životnosti objektů v [pomocí profilace metody z příkazového řádku](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md).

## <a name="to-collect-net-memory-data"></a>Ke shromažďování dat paměti .NET

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.

2. Na *výkonnostní relace* **stránky vlastností** dialogové okno, klikněte na tlačítko **Obecné** a vyberte **.NET shromažďování informací o přidělení objekt** zaškrtávací políčko.

3. Chcete-li shromažďovat data doba platnosti objektů .NET, vyberte **taky shromažďovat informace o doba života objektu rozhraní .NET** zaškrtávací políčko.

## <a name="common-tasks"></a>Běžné úlohy

Můžete zadat další možnosti v *výkonnostní relace *** stránky vlastností** dialogové okno relace výkonu. Chcete-li otevřít toto dialogové okno:

- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a pak klikněte na tlačítko **vlastnosti**.

Úkoly v následující tabulce popisují možnosti, které můžete zadat v *výkonnostní relace *** stránky vlastností** dialogové okno při shromažďování dat paměti .NET.

|Úloha|Související obsah|
|----------|---------------------|
|Na **Obecné** zadejte pojmenování podrobnosti vygenerovaný soubor profilování dat (.vsp).|- [Shromažďování dat paměti přidělení a dobu života rozhraní .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />- [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|
|Na **spusťte** vyberte aplikaci spustit, pokud máte více .exe projekty v řešení pro kód.|- [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **sledováním interakce vrstev** přidejte ADO.NET data volání do profilace spustit.|- [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|
|Na **události systému Windows** zadejte jeden nebo více událostí trasování událostí pro Windows (ETW) ke shromažďování dat vzorkování.|- [Postupy: shromažďování dat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|
|Na **čítačů systému Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do data profilování jako značky.|- [Postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|
|Na **Upřesnit** určete verzi modulu runtime rozhraní .NET Framework profilu, pokud vaše aplikace moduly pomocí více verzí. Ve výchozím nastavení je první verze načíst profilovaným.|- [Postupy: Zadejte modul runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|

## <a name="instrumentation-tasks"></a>Instrumentace úlohy

Úkoly v následující tabulce jsou možnosti v **stránky vlastností** okno, které jsou specifické pro profilace pomocí metody instrumentace.

|Úloha|Související obsah|
|----------|---------------------|
|Na **binární soubory** stránky, zadejte umístění pro instrumentovaného kopií modulů. Ve výchozím nastavení původní binární soubory přesunou do zálohovací složky.|- [Postupy: přemístění instrumentovaných binárních souborů](../profiling/how-to-relocate-instrumented-binaries.md)|
|Na **instrumentace** stránky, vyloučit malé funkce z profilace ke snížení profilace režie, profil kódu jazyka JavaScript na webových stránkách ASP.NET a zadat příkazy, pomocí příkazového řádku před a po instrumentace proces.|- [Postupy: vyloučení nebo zahrnutí funkce CShort z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />- [Postupy: profilování kódu JavaScript ve webové stránky](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />- [Postupy: Zadejte příkazy před a po instrumentaci](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|
|Na **čítače CPU** stránky, zadejte jeden nebo více čítače výkonu procesoru pro přidání do data profilování.|- [Postupy: shromažďování dat čítačů procesoru](../profiling/how-to-collect-cpu-counter-data.md)|
|Na **Upřesnit** zadejte jakékoli další VSInstr.exe požadované možnosti, jako jsou možnosti, které chcete zahrnout nebo vyloučit konkrétní funkce. Další informace o možnostech vsinstr – najdete v tématu [vsinstr –](../profiling/vsinstr.md)|- [Postupy: určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)<br />- [Postupy: omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)|

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Postupy: Výběr metod shromažďování](../profiling/how-to-choose-collection-methods.md)  
[Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)
