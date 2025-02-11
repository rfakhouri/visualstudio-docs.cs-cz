---
title: 'Profiler příkazový řádek: Otevřete nativní klientskou aplikaci, získání dat o souběžnosti'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e5aed651-afed-4b70-9a7e-1a6032cc614f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 6b20d239ee1be6cba9484e31efc95b1f38572b59
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2019
ms.locfileid: "67032927"
---
# <a name="how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: Spuštění samostatné nativní aplikace s profilerem za účelem shromažďování dat souběžnosti pomocí příkazového řádku
Toto téma popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci spuštění nativní samostatné (klientské) aplikaci a shromažďování dat souběžnosti procesů a vláken.

 Relace profilování obsahuje následující části:

- Spuštění aplikace s profilerem

- Řízení sběru dat

- Ukončení relace profilování

> [!NOTE]
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.

## <a name="start-the-application-with-the-profiler"></a>Spuštění aplikace s profilerem
 Chcete-li spustit cílovou aplikaci s profilerem, použijete [VSPerfCmd.exe](../profiling/vsperfcmd.md) **/start** a **/spuštění** možnosti, jak inicializovat Profiler a spusťte aplikaci. Můžete zadat **/start** a **/spuštění** a jejich příslušné volby. Můžete také přidat **/globaloff** možnost pozastavit shromažďování dat na začátku cílové aplikace. Pak použijete **globalon** Chcete-li začít shromažďovat data.

#### <a name="to-start-an-application-with-the-profiler"></a>Spuštění aplikace s profilerem

1. Na příkazovém řádku zadejte následující příkaz:

     [Nástroj VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/output:** `OutputFile` [`Options`]

     [/Output](../profiling/output.md) **:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění souboru dat profilování (.vsp).

     V následující tabulce můžete použít některou z možností **/start:concurrency** možnost.

    |Možnost|Popis|
    |------------|-----------------|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítač výkonu Windows má být shromážděn během profilování.|
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500.|
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (ETL) soubor.|

2. Spusťte cílovou aplikaci tak, že zadáte:

     **Nástroj VSPerfCmd**[/spuštění](../profiling/launch.md) **:** `AppName` [`Options`]

     V následující tabulce můžete použít některou z možností **/spuštění** možnost.

    |Možnost|Popis|
    |------------|-----------------|
    |[/ args](../profiling/args.md) **:** `Arguments`|Určuje řetězec, který obsahuje argumenty příkazového řádku, které se mají předat cílové aplikace.|
    |[/ Console](../profiling/console.md)|Spustí cílovou aplikaci příkazového řádku v samostatném okně.|
    |[targetclr](../profiling/targetclr.md) **:** `CLRVersion`|Určuje verzi modulu common language runtime (CLR), která má být profilována v případě aplikace načte bez více než jedna verze modulu CLR.|

## <a name="control-data-collection"></a>Řízení shromažďování dat
 Dokud je cílová aplikace spuštěna, lze sběr dat řídit spouštěním či pozastavováním zápisu dat do souboru s *VSPerfCmd.exe* možnosti. Řízením sběru dat může shromažďovat data pro určitou část provádění programu, například spouštění či ukončování aplikace.

#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat

- Následující páry možností v následující tabulce spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví ( **/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí ( **/processon**) nebo zastaví ( **/processoff**) sběr dat pro proces, který ID procesu (`PID`) určuje.|
    |[/ attach](../profiling/attach.md) **:** {`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[ **:** {`PID`&#124;`ProcName`}]|**/ attach** spustí sběr dat pro proces, který ID procesu (`PID`) nebo názvem procesu (*ProcName*) určuje. **/ detach** zastaví sběr dat pro zadaný proces nebo pro všechny procesy, pokud není zadán žádný proces.|

- Můžete také použít **VSPerfCmd.exe**[/mark](../profiling/mark.md) možnost k vložení profilovací značky do datového souboru. **/Mark** příkaz přidá identifikátor, časové razítko a volitelný uživatelem definovaný textový řetězec. Značky lze použít k filtrování dat v zobrazení data a sestavy profileru.

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování
 Chcete-li ukončit relaci profilování, profiler nesmí pokračovat ve shromažďování dat. Zastavit shromažďování dat souběžnosti zavřením profilované aplikace nebo zavoláním **VSPerfCmd / detach** možnost. Poté je zapotřebí vyvolat **VSPerfCmd/Shutdown** možnost se profiler vypne a uzavře soubor dat profilování.

#### <a name="to-end-a-profiling-session"></a>Chcete-li ukončit relaci profilování

1. Zadáním následujícího příkazu na příkazovém řádku nebo ukončením odpojte profiler od cílové aplikace:

     **Nástroj VSPerfCmd / odpojení**

2. Vypněte profiler zadáním následujícího příkazu na příkazovém řádku:

     **Nástroj VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)