---
title: Připojení profileru k aplikaci .NET ke shromažďování dat souběžnosti | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fdd41576-797e-4312-8520-fee7bb767e4a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 9b4703b2dd86056b2c79b8e50f8169a0b9fd9648
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431532"
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: Připojení profileru k samostatné aplikaci .NET Framework ke shromažďování dat souběžnosti pomocí příkazového řádku
Tento článek popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci k připojení profileru k běžící samostatné (klientské) aplikaci rozhraní .NET Framework a shromažďování dat souběžnosti procesů a vláken.

> [!NOTE]
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [názorný postup: Použití rozhraní API profileru](../profiling/walkthrough-using-profiler-apis.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého. Další informace najdete v tématu [zadejte cestu k nástroji příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

 Zatímco je profiler připojen k aplikaci, lze pozastavit a obnovit sběr dat. Chcete-li ukončit relaci profilování, musí profiler již připojen k aplikaci a Profiler musí být explicitně vypnut.

## <a name="attach-the-profiler"></a>Připojení profileru

#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Připojení profileru k běžící aplikaci rozhraní .NET Framework

1. Otevřete okno příkazového řádku.

2. Spusťte profiler. Typ:

     [Nástroj VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/output:** `OutputFile` [`Options`]

     [/Output](../profiling/output.md)**:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění souboru dat profilování (.vsp).

     Můžete použít některý z těchto možností s **/start:concurrency** možnost.

    |Možnost|Popis|
    |------------|-----------------|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítač výkonu Windows má být shromážděn během profilování.|
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500 ms.|
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (ETL) soubor.|

3. Spusťte cílovou aplikaci standardním způsobem.

4. Připojení profileru k cílové aplikaci. Typ:

     **Nástroj VSPerfCmd / připojit:** `PID` [**/lineoff**] [**targetclr:**`Version`]

    - `PID` Určuje ID procesu cílové aplikace. ID všech spuštěných procesů lze zobrazit ve Správci úloh Windows.

    - [/ lineoff](../profiling/lineoff.md) zakáže kolekci čísel datového řádku.

    - [targetclr](../profiling/targetclr.md) **:** `Version` Určuje verzi modulu common language runtime (CLR) do profilu je do aplikace načtena více než jedna verze modulu runtime. Volitelné.

## <a name="control-data-collection"></a>Řízení shromažďování dat
 Dokud je cílová aplikace spuštěna, lze sběr dat řídit spouštěním či pozastavováním zápisu dat do souboru s použitím *VSPerfCmd.exe* možnosti. Řízení sběru dat umožňuje shromažďovat data pro určitou část provádění programu, například spouštění či ukončování aplikace.

#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat

- Následující páry *VSPerfCmd.exe* možností spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví (**/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) sběr dat pro proces určený identifikátorem procesu (`PID`).|
    |[/ attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ attach** spustí sběr dat pro proces určený identifikátorem procesu (`PID`) nebo názvem procesu (ProcName). **/ detach** zastaví sběr dat pro zadaný proces nebo pro všechny procesy, pokud konkrétní proces není zadán.|

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování
 Chcete-li ukončit relaci profilování, profiler nesmí pokračovat ve shromažďování dat. Zastavit shromažďování dat od aplikace profilované za použití metody souběžnosti jejím ukončením nebo vyvoláním **VSPerfCmd / detach** možnost. Poté je zapotřebí vyvolat **VSPerfCmd/Shutdown** možnost profiler vypne a uzavře soubor dat profilování. **VSPerfClrEnv / off** příkaz vymaže proměnné prostředí profilování.

#### <a name="to-end-a-profiling-session"></a>Chcete-li ukončit relaci profilování

1. Proveďte jednu z následujících-li odpojit profiler od cílové aplikace.

    - Typ **VSPerfCmd / odpojení**

         -nebo-

    - Ukončete cílovou aplikaci.

2. Vypněte profiler. Typ:

     Nástroj VSPerfCmd [ /Shutdown](../profiling/shutdown.md)
