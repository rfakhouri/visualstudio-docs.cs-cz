---
title: "Vlastnosti výkonnostní relace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools,properties
- property pages,Profiling Tools
- performance tools, performance session properties
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8aaad070a7d50ca8fa4bba5741176121c72027fe
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="performance-session-properties"></a>Vlastnosti výkonnostní relace

A **výkonnostní relace** vám umožní nakonfigurovat nastavení, která určují, jak je vytvořený profil aplikace. Ukládá také sestavy, které jsou generovány pro relace profilování.

Vytvoříte **výkonnostní relace** spuštěním **Průvodce výkonu** ručně vytvořit relaci. **Výkonnostní relace** se zobrazí v **prohlížeč výkonu** po **výkonnostní relace** byla vytvořena.

Chcete-li zobrazit **výkonnostní relace** vlastnosti, vyberte název relace v **prohlížeč výkonu**, pravým tlačítkem myši a pak vyberte **vlastnosti**.

Výkonnostní relace má následující stránky vlastností:

## <a name="general"></a>Obecné

Toto nastavení umožňuje vybrat metoda, můžete přidat kolekci objektů .NET a životnosti a zadejte umístění sestavy výchozí profilování a pojmenování konvence.

Další informace naleznete v tématu:

[Postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)

[Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)

 [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)

## <a name="launch"></a>Spuštění

Tato nastavení umožňují vybrat ze seznamu binárních souborů a určit pořadí spuštění binárních souborů.

Další informace najdete v tématu [postupy: určení binárního souboru spuštění](../profiling/how-to-specify-the-binary-to-start.md)

## <a name="sampling"></a>Vzorkování

Toto nastavení umožňuje vybrat intervalu vzorkování událostí a vzorkování při vzorkování slouží jako metodu profilování. Událost vzorku se používá ke shromažďování data profilování v zadaném intervalu. Například pokud událost vzorku hodinových cyklů a interval vzorkování je nastaven na hodnotu 10 000 000 pak profilace data se shromažďují po každých 10 milionů taktovací cykly. K dispozici jsou následující čtyři typy ukázkové události:

- Hodiny cykly - procesoru vázaný problémy
- Problémy související chyby stránky - paměti
- Systém volání - pro vstupně-výstupních operací souvisejících problémů
- Čítače výkonu – pro problémy s výkonem nízké úrovně
- Další ukázkové události lze zadat podle dostupných čítačů výkonu

Další informace najdete v tématu [postupy: výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)

## <a name="binary"></a>binární
Tato nastavení umožňují určit, zda má být instrumentované binární přemístit na jiné umístění. Například pokud jsou profilace My.DLL a zvolit nepoužívání přemístit instrumentované binární, je vytvořit si záložní kopii My.DLL s názvem My.Orig.DLL. Následně je upravit My.DLL vložením sondy shromažďovat data. Pokud se rozhodnete přemístit instrumentované binární, původní binárního souboru se nepřejmenuje a instrumentované binární soubor zkopírován do zadaného umístění pro použití během instrumentace.

Další informace najdete v tématu [postupy: určení binárního souboru spuštění](../profiling/how-to-specify-the-binary-to-start.md)

## <a name="tier-interactions"></a>Interakcí vrstev

Další informace najdete v tématu [shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)

## <a name="instrumentation"></a>Instrumentace

Tato nastavení umožňují shromažďovat data o výkonu pro JScript kód v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové stránky a zadat jakýkoli **před instrumentací** a **po instrumentaci** události, které mají být provedeny před nebo po instrumentace proces.

Další informace naleznete v tématu:

[Postupy: profilování kódu JavaScript ve webové stránky](../profiling/how-to-profile-javascript-code-in-web-pages.md)

[Postupy: Zadejte příkazy před a po instrumentaci](../profiling/how-to-specify-pre-and-post-instrument-commands.md)

## <a name="cpu-counters"></a>Čítače CPU

Tato nastavení umožňují shromažďovat data o čítačích výkonu procesoru při použití metoda profilování instrumentace. Přenosné čítače výkonu jsou k dispozici bez ohledu na návrh procesoru nebo výrobce. Platforma události jsou specifické pro procesor návrhu a výrobce. Další informace o čítačích výkonu na čipu naleznete v dokumentaci k specifické procesory.

Další informace najdete v tématu [postupy: shromažďování dat čítačů procesoru](../profiling/how-to-collect-cpu-counter-data.md)

## <a name="windows-events"></a>Windows Events

Při vytváření profilu, můžete shromažďovat údaje ze zprostředkovatelů trasování událostí. Data můžete zobrazit pomocí nástroje příkazového řádku VSPerfReport.exe `/calltrace` možnost. Další informace o trasování událostí pro Windows (ETW) najdete v tématu [o trasování událostí](http://go.microsoft.com/fwlink/?linkid=90752).

Další informace naleznete v tématu:

[Postupy: shromažďování trasování událostí pro Windows (ETW) dat](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)

[Vsperfreport –](../profiling/vsperfreport.md).

## <a name="windows-counters"></a>Čítače systému Windows

Tato možnost umožňuje shromažďovat data z čítače sledování výkonu systému Windows. Shromažďování těchto dat, zaškrtněte políčko s názvem bez přípony **shromažďování čítačů výkonu systému Windows**. Interval sběru lze nastavit v **Interval sběru** pole. **Čítač kategorie** a **Instance** může být také dostupný. Některé výchozí čítače sledování výkonu systému Windows jsou k dispozici.

 Další informace najdete v tématu [postupy: shromažďování dat čítačů Windows](../profiling/how-to-collect-windows-counter-data.md).

## <a name="advanced"></a>Upřesnit

Tato nastavení umožňují přidat možnosti proces instrumentace zadáním jednoho nebo více možností z [vsinstr –](../profiling/vsinstr.md) profilace nástroj příkazového řádku. Můžete také zadejte verzi běžné modulu Runtime profilu, pokud aplikace používá více než jedna verze.

Další informace naleznete v tématu:

[Postupy: Zadejte modul Runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)

[Postupy: určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)

## <a name="see-also"></a>Viz také

[Přehledy](../profiling/overviews-performance-tools.md)  
[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Řízení shromažďování dat](../profiling/controlling-data-collection.md)