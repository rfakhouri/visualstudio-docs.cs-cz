---
title: 'Postupy: spuštění samostatné aplikace rozhraní .NET Framework s Profilerem ke shromažďování dat paměti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3bc53041-91b7-4ad0-8413-f8bf2c4b3f5e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 456e8fff1b4e484648c1e30a9b588a4f5923fc91
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line"></a>Postupy: Spuštění samostatné aplikace rozhraní .NET Framework s profilerem za účelem shromáždění dat paměti pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci spuštění samostatné (klientské) aplikace rozhraní .NET Framework a shromažďování dat paměti.  
  
 Relace profilování má tři části:  
  
-   Spouštění aplikace pomocí profileru.  
  
-   Shromažďování údajů o profilování.  
  
-   Ukončení relace profilování.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-application-with-the-profiler"></a>Spouštění aplikace s Profilerem  
 Chcete-li spustit cílová aplikace pomocí profileru, použijte **VSPerfCmd.exe/start** a **/spusťte** možnosti k inicializaci profileru a spuštění aplikace. Můžete zadat **/start** a **/spusťte** a jejich odpovídající možnosti na jednoho příkazového řádku.  
  
 Můžete také přidat **/globaloff** možnosti pro pozastavení shromažďování dat na začátku cílová aplikace. Pak použijete **/globalon** zahájíte shromažďovat data.  
  
#### <a name="to-start-an-application-by-using-the-profiler"></a>Spuštění aplikace pomocí profileru  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:sample output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: Ukázka** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
  
3.  Spusťte cílová aplikace. Typ:  
  
     **VSPerfCmd**[/spusťte](../profiling/launch.md) **:** `appName` **/gc:**{**přidělení**&#124;**doba platnosti** }[`Options`]    
  
    -   [/Gc](../profiling/gc-vsperfcmd.md)**:** `Keyword` se vyžaduje možnost ke shromažďování dat paměti .NET Framework. Parametr – klíčové slovo určuje, jestli ke shromažďování dat přidělení paměti nebo shromažďovat přidělování paměti a životnosti objektů.  
  
        |– Klíčové slovo|Popis|  
        |-------------|-----------------|  
        |**Přidělení**|Shromažďování dat paměti přidělení jenom.|  
        |**Doba platnosti**|Shromážděte přidělování paměti a životnosti objektů.|  
  
     Můžete použít některou z následujících možností s **/spusťte** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Určuje řetězec, který obsahuje argumenty příkazového řádku mají být předány cílová aplikace.|  
    |[/ Console](../profiling/console.md)|Spustí cílová aplikace příkazového řádku v samostatném okně.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Určuje verzi common language runtime (CLR) profilu při načtení více než jednu verzi modulu runtime v aplikaci.|  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Pokud cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, který je zadán Identifikátor procesu (`PID`).|  
    |[/ připojit](../profiling/attach.md) **:** `PID` [/ odpojit](../profiling/detach.md)|**/ připojit** spustí ke shromažďování dat pro proces, který je zadán `PID` (ID procesu). **/ detach** zastaví sběr dat pro všechny procesy.|  
  
-   Můžete také **VSPerfCmd.exe**[/označit](../profiling/mark.md) možnost vložit do datového souboru profilování značky. **/Označit** příkaz přidá identifikátor, časové razítko a volitelné uživatelem definované textový řetězec. Značky mohou být použity k filtrování data.  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, musí být profileru odpojit od všech PROFILOVANÉHO procesů a profileru musí být explicitně vypnuté. Můžete odpojit profileru z aplikace, která byla profilovaným pomocí metody vzorkování ukončením aplikace nebo voláním **VSPerfCmd / detach** možnost. Potom zavolejte **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jeden z následujících kroků k odpojení profileru z cílová aplikace:  
  
    -   Zavřete cílová aplikace.  
  
         -nebo-  
  
    -   Typ **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru. Typ:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Viz také  
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)