---
title: 'Postupy: instrumentace na rozhraní .NET Framework služby a shromažďování dat paměti pomocí příkazového řádku profileru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2fa072fc-05fe-4420-99c0-51d2ea3ac4ce
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 03c676100487acb7aff9cb28071192ff6b04ed29
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-instrument-a-net-framework-service-and-collect-memory-data-by-using-the-profiler-command-line"></a>Postupy: Instrumentace služby rozhraní .NET Framework a shromažďování dat paměti pomocí příkazového řádku profileru
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci účelem instrumentace [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] služby a shromažďování údajů o využití paměti. Můžete shromáždit data přidělení paměti, nebo můžete shromáždit přidělování paměti a životnosti objektů.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Pomocí metody instrumentace nelze profilu služby, pokud nelze restartovat službu po spuštění počítače, tato služba, která spustit při spuštění operačního systému.  
>   
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. V 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="starting-the-profiling-session"></a>Spuštění relace profilování  
 Ke shromažďování dat výkonu z [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] služby, můžete použít [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k chybě při inicializaci příslušné proměnné prostředí a [VSInstr.exe](../profiling/vsinstr.md) nástroj pro vytvoření instrumentované kopie binárního souboru služby.  
  
 Ho nakonfigurovat pro profilace po restartování počítače, který je hostitelem služby. Musíte také spustit službu ručně ze Správce řízení služeb. Spusťte profileru a pak spusťte [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] služby.  
  
 Po provedení komponentu instrumentovaného paměti data jsou shromažďována automaticky do datového souboru. Můžete pozastavit a obnovit shromažďování dat během relace profilování.  
  
 K ukončení relace profilování, zavřete službu a explicitně vypnout profileru. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
#### <a name="to-begin-profiling-a-net-framework-service"></a>Chcete-li začít profilace služby rozhraní .NET Framework  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Použití **vsinstr –** nástroj pro generování instrumentovaného verzi binární.  
  
3.  Použití správce řízení služeb nahradit původní binární instrumentovaného verze. Ujistěte se, že služba typ spuštění nastavený na ruční.  
  
4.  Inicializujte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv –** {**/globaltracegc** &#124; **/globaltracegclife**}  
  
    -   **/globaltracegc** a **/globaltracegclife** Povolit shromažďování dat paměti přidělení a objekt životního cyklu.  
  
        |Možnost|Popis|  
        |------------|-----------------|  
        |**/globaltracegc**|Shromažďuje jenom data přidělení paměti.|  
        |**/globaltracegclife**|Shromažďuje údaje o přidělení a objekt životnost paměti.|  
  
5.  Restartujte počítač.  
  
6.  Otevřete okno příkazového řádku.  
  
7.  Spusťte profileru. Typ:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: trasování**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]      
  
    -   **/Start: kolizí** možnost inicializuje profileru.  
  
    -   **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro služby.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel, než je přihlášený uživatel. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Id relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/waitstart](../profiling/waitstart.md)[**:**`Interval`]|Určuje počet sekund pro čekání profileru k chybě při inicializaci předtím, než vrátí chybu. Pokud `Interval` není zadán, profileru čeká neomezenou dobu zaseknout. Ve výchozím nastavení **/start** vrátí okamžitě.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění profileru se shromažďování dat pozastavena, přidejte **/globaloff** možnost k **/start** příkazového řádku. Použití **/globalon** obnovit profilace.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Shromažďuje informace z čítače zadaný v konfiguračním výkon procesoru. Informace o čítači se přidá na data shromažďovaná v každé profilování události.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
8.  V případě potřeby spusťte službu.  
  
9. Připojení profileru ke službě. Typ:  
  
     **VSPerfCmd / připojit:**`PID`&#124;`ProcessName`  
  
    -   Zadejte ID procesu nebo název procesu služby. ID procesu a názvy všech spuštěných procesů můžete zobrazit ve Správci úloh systému Windows.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když je služba spuštěná, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru s **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno určeného ID vlákna (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, zavřete aplikaci, která běží instrumentovaného součásti, spusťte **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Zastavte službu ze Správce řízení služeb.  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
3.  Po dokončení všech profilace zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – /globaloff**  
  
     Modul instrumentovaného nahraďte původní. V případě potřeby znovu nakonfigurujte typ spouštění služby.  
  
4.  Restartujte počítač.  
  
## <a name="see-also"></a>Viz také  
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)