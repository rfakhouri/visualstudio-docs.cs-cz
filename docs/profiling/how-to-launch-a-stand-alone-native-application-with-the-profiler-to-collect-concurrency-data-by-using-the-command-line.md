---
title: 'Postupy: spuštění samostatné nativní aplikace s Profilerem za účelem shromažďování dat souběžnosti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: e5aed651-afed-4b70-9a7e-1a6032cc614f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: a71d7b656dc56d1bb92916d4b35f5fae39e05b77
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: Spuštění samostatné nativní aplikace s profilerem za účelem shromáždění dat souběžnosti pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci spuštění samostatné nativní (klientskou) aplikaci a shromažďování dat souběžnosti proces a přístup z více vláken.  
  
 Relace profilování má následující části:  
  
-   Spouštění aplikace s profilerem  
  
-   Řízení shromažďování dat  
  
-   Ukončení relace profilování  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Použití profileru na příkazovém řádku, je nutné přidat cestu nástroje do proměnné prostředí PATH z **příkazového řádku** okno, nebo přidejte k příkazu sám sebe. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-application-with-the-profiler"></a>Spouštění aplikace s Profilerem  
 Chcete-li spustit cílová aplikace s profilerem, použijte [VSPerfCmd.exe](../profiling/vsperfcmd.md)**/start** a **/spustit** možnosti k inicializaci profileru a spuštění aplikace. Můžete zadat **/start** a **/spusťte** a jejich odpovídající možnosti. Můžete také přidat **/globaloff** možnost pozastavit shromažďování dat na začátku cílová aplikace. Pak použijete **/globalon** zahájíte shromažďovat data.  
  
#### <a name="to-start-an-application-with-the-profiler"></a>Chcete-li aplikaci spustit s profilerem  
  
1.  Na příkazovém řádku zadejte následující příkaz:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency output:** `OutputFile` [`Options`]  
  
     [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     V následující tabulce se můžete použít některou z možností **/start:concurrency** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
2.  Cílová aplikace spusťte zadáním:  
  
     **VSPerfCmd**[/spusťte](../profiling/launch.md) **:** `AppName` [`Options`]    
  
     V následující tabulce se můžete použít některou z možností **/spusťte** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Určuje řetězec, který obsahuje argumenty příkazového řádku mají být předány cílová aplikace.|  
    |[/ Console](../profiling/console.md)|Spustí cílová aplikace příkazového řádku v samostatném okně.|  
    |[/targetclr](../profiling/targetclr.md) **:** `CLRVersion`|Určuje verzi common language runtime (CLR) profilu, pokud aplikace načte více než jedna verze modulu CLR.|  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru s možností VSPerfCmd.exe. Pomocí řízení shromažďování dat můžete shromažďování dat pro konkrétní součást spuštění programu, jako je například počáteční nebo vypnutí aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Dvojice možnosti uvedené v následující tabulce spustit a zastavit shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, ID procesu (`PID`) určuje.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, ID procesu (`PID`) nebo název procesu (*Nazev_procedury*) určuje. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán žádný proces.|  
  
-   Můžete také **VSPerfCmd.exe**[/označit](../profiling/mark.md) možnost vložit do datového souboru profilování značky. **/Označit** příkaz přidá identifikátor, časové razítko a volitelné uživatelem definované textový řetězec. Značky lze použít k filtrování dat v zobrazení dat a sestav profileru.  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat souběžnosti ukončením PROFILOVANÉHO aplikace nebo vyvoláním **VSPerfCmd / detach** možnost. Potom vyvolat **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Odpojte profileru z cílová aplikace ukončením ho nebo zadáním následujícího příkazu na příkazovém řádku:  
  
     **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru zadáním následujícího příkazu na příkazovém řádku:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)