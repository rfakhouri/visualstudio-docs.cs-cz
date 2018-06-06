---
title: 'Postupy: spuštění samostatné aplikace rozhraní .NET Framework s Profilerem ke shromažďování dat souběžnosti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 17a48848-bd3e-44ef-9971-e39836ff1df2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 8a44fd95ec8561df7de0970ac81446757f122121
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815715"
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: spuštění samostatné aplikace rozhraní .NET Framework s profilerem ke shromažďování dat souběžnosti pomocí příkazového řádku
Toto téma popisuje způsob používání nástrojů příkazového řádku balíku nástrojů pro profilaci sady [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ke spuštění samostatné (klientské) aplikace rozhraní .NET Framework a shromažďování dat procesu a souběžnosti vláken.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěné v *\Team Tools\Performance nástroje* podadresáři [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [zadejte cestu k nástroje příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Při profileru je připojen k aplikaci, můžete pozastavit a obnovit data kolekce. K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté.  
  
## <a name="start-the-application-with-the-profiler"></a>Spuštění aplikace s profilerem  
 Chcete-li spuštění cílové aplikace rozhraní .NET Framework s Profilerem, použijte *VSPerfClrEnv.exe* nastavit rozhraní .NET Framework profilace proměnné. Pak použijete VSPerfCmd **/start** a **/spusťte** možnosti k inicializaci profileru a spuštění aplikace. Můžete zadat **/start** a **/spusťte** a jejich odpovídající možnosti na jednoho příkazového řádku. Můžete také přidat **/globaloff** možnost příkazového řádku pro pozastavení shromažďování dat, když se spustí cílová aplikace. Pak použijete **/globalon** na samostatném řádku příkaz k shromažďovat data.  
  
#### <a name="to-start-an-application-with-the-profiler"></a>Spuštění aplikace s profilerem  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Spusťte profileru. Typ:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency**[**,**{**ResourceOnly**&#124;**ThreadOnly**}] **/ výstup:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md) možnost inicializuje profileru.  
  
        |||  
        |-|-|  
        |**/Start:Concurrency**|Umožňuje shromažďovat kolize prostředků a data spouštění vlákna.|  
        |**/Start:Concurrency resourceonly**|Umožňuje shromažďovat pouze data kolize prostředků.|  
        |**/Start:Concurrency threadonly**|Umožňuje shromažďovat pouze data spouštění vlákna.|  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:concurrency** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`domain\`]`username`|Určuje nepovinné domény a uživatelské jméno účtu, který chcete povolit přístup k profileru.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v samostatné (. *ETL*) souboru.|  
  
3.  Spusťte cílová aplikace. Typ:  
  
     **VSPerfCmd**[/spusťte](../profiling/launch.md) **:** `AppName` [`Options`] [`Sample Event`]  
  
     Můžete použít některou z následujících možností s **/spusťte** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Určuje řetězec, který obsahuje argumenty příkazového řádku mají být předány cílová aplikace.|  
    |[/ Console](../profiling/console.md)|Spustí cílová aplikace příkazového řádku v samostatném okně.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Určuje verzi common language runtime (CLR) profilu při načtení více než jednu verzi modulu runtime v aplikaci.|  
  
## <a name="control-data-collection"></a>Řízení shromažďování dat  
 Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí *VSPerfCmd.exe* možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, například spuštění nebo ukončení aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
1.  Následující dvojice *VSPerfCmd.exe* možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném příkazového řádku. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí ID procesu (`PID`) nebo název procesu (Nazev_procedury). **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="end-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat souběžnosti ukončením PROFILOVANÉHO aplikace nebo vyvoláním **VSPerfCmd / detach** možnost. Potom vyvolat **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jednu z následujících způsobů odpojit profileru z cílové aplikace.  
  
    -   Zavřete cílová aplikace.  
  
         -nebo-  
  
    -   Typ **VSPerfCmd / odpojit**  
  
2.  Ukončete profiler.  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Viz také:  
 [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)