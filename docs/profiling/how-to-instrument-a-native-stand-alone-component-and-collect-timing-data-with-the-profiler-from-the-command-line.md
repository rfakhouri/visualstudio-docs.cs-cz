---
title: "Postupy: instrumentace nativní samostatné součásti a shromažďování dat profileru z příkazového řádku časování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36883074-9be8-4e90-a66f-7e87f21fcd30
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8887b9ef7663f3c1748c4de3571a076a89d63087
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-instrument-a-native-stand-alone-component-and-collect-timing-data-with-the-profiler-from-the-command-line"></a>Postupy: Instrumentace nativní samostatné součásti a shromažďování dat časování z příkazového řádku profileru
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje instrumentace nativní součásti, jako je soubor .exe nebo .dll C++ a shromažďování podrobných dat časování.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Shromažďování podrobných dat časování pomocí metody instrumentace z součásti, můžete použít [VSInstr.exe](../profiling/vsinstr.md) nástroj pro generování instrumentovaného verzi komponentu. Potom je nutné spustit profileru. Po provedení komponentu instrumentovaného časování data jsou shromažďována automaticky do datového souboru. Můžete pozastavit a obnovit shromažďování dat během relace profilování.  
  
 K ukončení relace profilování, zavřete cílová aplikace a poté explicitně vypněte profileru.  
  
## <a name="starting-the-profiling-session"></a>Spuštění relace profilování  
  
#### <a name="to-start-profiling-by-using-the-instrumentation-method"></a>Ke spuštění profilování pomocí metody instrumentace  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Použití **vsinstr –** nástroj pro generování instrumentovaného verzi cílové aplikace.  
  
3.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:trace output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: trasování** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile`Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít jeden nebo více z následujících možností s **/start:trace** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je vyžaduje jenom v případě, že je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích. Tato možnost je povinná, pokud je aplikace spuštěna v jiné relaci. Identifikátor relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění, které profileru se shromažďováním dat. pozastavena. Použití [/globalon](../profiling/globalon-and-globaloff.md) obnovit profilace.|  
    |[/ Čítač](../profiling/counter.md) **:**`Config`|Shromažďuje informace z čítače výkonu procesoru, který je uveden v `Config`. Čítač informace vkládá data, která se shromažďují v každé profilování události.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
4.  Spusťte cílová aplikace typické způsobem.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Pokud cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, který je zadán Identifikátor procesu (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:**`TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno, která je zadána ID vlákna (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, ukončete aplikaci, která běží komponentu instrumentované a potom zavolejte **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Zavřete cílová aplikace.  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
## <a name="see-also"></a>Viz také  
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)