---
title: 'Postupy: Spusťte samostatné aplikace rozhraní .NET Framework s Profiler ke shromažďování dat paměti pomocí příkazového řádku | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3bc53041-91b7-4ad0-8413-f8bf2c4b3f5e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 18e90e44da8b36dbc4824817c7f13bbe423a2c12
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56614178"
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line"></a>Postupy: Spuštění samostatné aplikace rozhraní .NET Framework s profilerem ke shromažďování dat paměti pomocí příkazového řádku
Toto téma popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci spuštění samostatné (klientské) aplikaci rozhraní .NET Framework a shromažďování dat paměti.

 Relace profilování má tři části:

-   Spuštění aplikace pomocí profileru.

-   Shromažďování dat profilování.

-   Ukončení relace profilování.

> [!NOTE]
>  Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.

## <a name="start-the-application-with-the-profiler"></a>Spuštění aplikace s profilerem
 Chcete-li spustit cílovou aplikaci pomocí profileru, je použít **VSPerfCmd.exe/start** a **/spuštění** možnosti pro inicializaci profileru a spuštění aplikace. Můžete zadat **/start** a **/spuštění** a jejich příslušné volby v jednom příkazovém řádku.

 Můžete také přidat **/globaloff** možnost pozastavit shromažďování dat na začátku cílové aplikace. Pak použijete **globalon** spustit shromažďování data.

#### <a name="to-start-an-application-by-using-the-profiler"></a>Spusťte aplikaci pomocí profileru

1. Otevřete okno příkazového řádku.

2. Spusťte profiler. Typ:

    **/Start:sample VSPerfCmd/output:** `OutputFile` [`Options`]

   - [/Start](../profiling/start.md)**: Ukázka** možnost inicializuje profiler.

   - [/Output](../profiling/output.md)**:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění souboru dat profilování (.vsp).

     Můžete použít některý z těchto možností s **/start:sample** možnost.

   | Možnost | Popis |
   | - | - |
   | [/wincounter](../profiling/wincounter.md) **:** `WinCounterPath` | Určuje čítač výkonu Windows má být shromážděn během profilování. |
   | [/automark](../profiling/automark.md) **:** `Interval` | Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500 ms. |


3. Spusťte cílovou aplikaci. Zadejte:

    **VSPerfCmd**  [/launch](../profiling/launch.md) **:** `appName` **/gc:**{**allocation**&#124;**lifetime**}[`Options`]

   - [/GC –](../profiling/gc-vsperfcmd.md)**:** `Keyword` možnost je vyžadována ke shromažďování dat paměti .NET Framework. Parametr – klíčové slovo určuje, zda chcete shromažďovat data o přidělování paměti nebo získat informace o přidělování paměti a životnosti objektů.

     |Klíčové slovo|Popis|
     |-------------|-----------------|
     |**přidělení**|Shromážděte data o přidělování paměti pouze.|
     |**lifetime**|Shromážděte o přidělování paměti a životnosti objektů.|

     Můžete použít některý z těchto možností s **/spuštění** možnost.

   |Možnost|Popis|
   |------------|-----------------|
   |[/ args](../profiling/args.md) **:** `Arguments`|Určuje řetězec, který obsahuje argumenty příkazového řádku, které se mají předat cílové aplikace.|
   |[/ Console](../profiling/console.md)|Spustí cílovou aplikaci příkazového řádku v samostatném okně.|
   |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (ETL) soubor.|
   |[targetclr](../profiling/targetclr.md) **:** `Version`|Určuje verzi modulu common language runtime (CLR), která má být profilována je do aplikace načtena více než jedna verze modulu runtime.|

## <a name="control-data-collection"></a>Řízení shromažďování dat
 Pokud je cílová aplikace spuštěna, lze sběr dat řídit spouštěním či pozastavováním zápisu dat do souboru s použitím *VSPerfCmd.exe* možnosti. Řízení sběru dat umožňuje shromažďovat data pro určitou část provádění programu, například spouštění či ukončování aplikace.

#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat

-   Následující páry možností spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví (**/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) sběr dat pro proces určený identifikátorem procesu (`PID`).|
    |[/ attach](../profiling/attach.md) **:** `PID` [/ odpojení](../profiling/detach.md)|**/ attach** spustí sběr dat pro proces určený pomocí `PID` (ID procesu). **/ detach** zastaví sběr dat pro všechny procesy.|

-   Můžete také použít **VSPerfCmd.exe**[/mark](../profiling/mark.md) možnost k vložení profilovací značky do datového souboru. **/Mark** příkaz přidá identifikátor, časové razítko a volitelný uživatelem definovaný textový řetězec. Značky lze použít k filtrování dat.

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování
 Chcete-li ukončit relaci profilování, musí být profiler odpojen od všech profilovaných procesů a profiler musí být explicitně vypnut. Je-li odpojit profiler od aplikace profilované za použití metody vzorkování ukončením aplikace nebo zavoláním **VSPerfCmd / detach** možnost. Poté je zapotřebí zavolat **VSPerfCmd/Shutdown** možnost se profiler vypne a uzavře soubor dat profilování. **VSPerfClrEnv / off** příkaz vymaže proměnné prostředí profilování.

#### <a name="to-end-a-profiling-session"></a>Chcete-li ukončit relaci profilování

1.  Proveďte jeden z následujících kroků-li odpojit profiler od cílové aplikace:

    -   Ukončete cílovou aplikaci.

         -nebo-

    -   Typ **VSPerfCmd / odpojení**

2.  Vypněte profiler. Typ:

     **Nástroj VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)

## <a name="see-also"></a>Viz také:
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)