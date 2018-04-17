---
title: 'Postupy: spuštění samostatné aplikace s Profilerem a shromáždění statistik aplikace pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 52dcee2b-f178-4a76-bddc-e36c50bfcb78
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9b8afcf8b16925e0bfa9bc473f6f3d0410bd7130
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line"></a>Postupy: Spuštění samostatné aplikace s profilerem a shromáždění statistik aplikace pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci spuštění samostatné (klientskou) aplikaci a shromažďování statistik výkonu pomocí metody vzorkování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Přidání dat interakce vrstev pro spuštění profilování vyžaduje konkrétní postupy s příkazového řádku nástroje pro profilaci. V tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)  
  
 Chcete-li použít nástroje příkazového řádku profileru, musíte přidat cestu do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Nástroje pro profilaci můžete spustit na počítači nainstalovanou aplikaci Visual Studio z příkazového okna Visual Studio.  
  
1.  Pokud používáte nástrojů pro profilaci počítači, kde je Visual Studio nainstalována okno sady Visual Studio příkazů správné cesty. Na **nástroje** nabídce zvolte **VS příkazového řádku**  
  
> [!NOTE]
>  Nástroje příkazového řádku balíku nástrojů pro profilaci jsou umístěny v podadresáři \Team Tools\Performance Tools instalačního adresáře sady Visual Studio. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musíte přidat cestu do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-application-with-the-profiler"></a>Spouštění aplikace s Profilerem  
 Spuštění cílová aplikace pomocí profileru, použijte VSPerfCmd **/start** a **/spusťte** možnosti k inicializaci profileru a spuštění aplikace. Můžete zadat **/start** a **/spusťte** a jejich odpovídající možnosti na jednoho příkazového řádku.  
  
 Můžete také přidat **/globaloff** možnost pozastavit shromažďování dat na začátku cílová aplikace. Pak použijete **/globalon** zahájíte shromažďovat data.  
  
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
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
3.  Spusťte cílová aplikace. Typ:**VSPerfCmd /launch:** `appName` [`Options`] [`Sample Event`]  
  
     Můžete použít jeden nebo více z následujících možností s **/spusťte** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Určuje řetězec, který obsahuje argumenty příkazového řádku mají být předány cílová aplikace.|  
    |[/ Console](../profiling/console.md)|Spustí cílová aplikace příkazového řádku v samostatném okně.|  
  
     Ve výchozím nastavení, data výkonu vzorkovat hodin každých 10 000 000-zastavit procesoru cykly. Toto je přibližně jednou na procesor 1GHz každých 10 sekund. Můžete zadat jednu z následujících možností změnit interval cyklus hodiny nebo zadejte jiný vzorkování událostí.  
  
    |Událost vzorku|Popis|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Interval vzorkování se změní na počet cyklů-Zastavit hodiny, které jsou určené `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Změny událostí vzorkování chyb stránek. Pokud `Interval` je zadané, nastaví počet chyb stránek mezi vzorky. Výchozí hodnota je 10.|  
    |[/ sys](../profiling/sys-vsperfcmd.md)[**:**`Interval`]|Změny událostí vzorkování systémová volání z procesu s jádrem operačního systému (syscalls). Pokud `Interval` je zadané, nastaví počet volání mezi vzorky. Výchozí hodnota je 10.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Změny událostí vzorkování a intervalu čítače výkonu procesoru a interval, který jsou určené v `Config`.|  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Pokud cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do datového souboru profileru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**  `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí `PID` nebo název procesu (Nazev_procedury). **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru připojena k žádné PROFILOVANÉHO proces a profileru musí být explicitně vypnuté. Můžete odpojit profileru z aplikace, která byla profilovaným pomocí metody vzorkování ukončením aplikace nebo voláním **VSPerfCmd / detach** možnost. Potom zavolejte **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jeden z následujících kroků k odpojení profileru z cílová aplikace:  
  
    -   Zavřete cílová aplikace.  
  
         -nebo-  
  
    -   Typ **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru. Typ:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Viz také  
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)