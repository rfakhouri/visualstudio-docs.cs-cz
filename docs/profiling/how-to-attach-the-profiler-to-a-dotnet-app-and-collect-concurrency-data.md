---
title: 'Postupy: připojení profileru k samostatné aplikaci .NET Framework ke shromažďování dat souběžnosti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: fdd41576-797e-4312-8520-fee7bb767e4a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: f727e2a06fa2e5798de84c7b6ee6d97bfb2a4558
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815282"
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: připojení profileru k samostatné aplikaci .NET Framework ke shromažďování dat souběžnosti pomocí příkazového řádku
Tento článek popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k aplikaci spuštěné samostatné (klient) rozhraní .NET Framework a shromažďování dat souběžnosti proces a přístup z více vláken.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěné v *\Team Tools\Performance nástroje* podadresáři [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [zadejte cestu k nástroje příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Při profileru je připojen k aplikaci, můžete pozastavit a obnovit data kolekce. K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté.  
  
## <a name="attach-the-profiler"></a>Připojení profileru  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Chcete-li připojení profileru k spuštěné aplikace rozhraní .NET Framework  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Spusťte profileru. Typ:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency output:** `OutputFile` [`Options`]  
  
     [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:concurrency** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
3.  Spusťte cílová aplikace typické způsobem.  
  
4.  Připojení profileru k cílové aplikaci. Typ:  
  
     **VSPerfCmd / připojit:** `PID` [**/lineoff**] [**/targetclr:**`Version`]  
  
    -   `PID` Určuje ID procesu cílová aplikace. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
    -   [/lineoff](../profiling/lineoff.md) zakáže shromažďování dat číslo řádku.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version` určuje verzí common language runtime (CLR) má profil při načtení více než jednu verzi modulu runtime v aplikaci. Volitelné.  
  
## <a name="control-data-collection"></a>Řízení shromažďování dat  
 Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí *VSPerfCmd.exe* možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například počáteční nebo vypnutí aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice *VSPerfCmd.exe* možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném příkazového řádku. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí ID procesu (`PID`) nebo název procesu (Nazev_procedury). **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="end-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat z aplikace profilovaným s metoda souběžného zpracování ukončením aplikace nebo vyvoláním **VSPerfCmd / detach** možnost. Potom vyvolat **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jednu z následujících způsobů odpojit profileru z cílové aplikace.  
  
    -   Typ **VSPerfCmd / odpojit**  
  
         -nebo-  
  
    -   Zavřete cílová aplikace.  
  
2.  Vypněte profileru. Typ:  
  
     Vsperfcmd – [ /Shutdown](../profiling/shutdown.md)
