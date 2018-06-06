---
title: 'Postupy: instrumentace samostatné součásti rozhraní .NET Framework a shromažďování dat profileru z příkazového řádku časování | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b7dcc27b-45c6-4302-9552-6fa5b1e94b56
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: d9a9e26829f30eaeb9133a022ca8d1af694fb1c9
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815805"
---
# <a name="how-to-instrument-a-stand-alone-net-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line"></a>Postupy: instrumentace samostatné součásti rozhraní .NET Framework a shromažďování dat časování profileru z příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci k instrumentace součásti rozhraní .NET Framework, jako. *exe* nebo. *knihovny DLL* souboru a shromažďování podrobných dat časování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Nástroje příkazového řádku nástroje profilace jsou umístěné v *\Team Tools\Performance nástroje* podadresáři [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [zadejte cestu k nástroje příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Přidání dat interakce vrstev pro spuštění profilování vyžaduje konkrétní postupy s příkazového řádku nástroje pro profilaci. V tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Shromažďování podrobných dat časování pomocí metody instrumentace z součásti rozhraní .NET Framework, můžete použít [VSInstr.exe](../profiling/vsinstr.md) nástroj pro generování instrumentovaného verzi součásti a [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k chybě při inicializaci profilování proměnné prostředí. Potom je nutné spustit profileru.  
  
 Po provedení komponentu instrumentovaného časování data jsou shromažďována automaticky do datového souboru. Můžete pozastavit a obnovit shromažďování dat během relace profilování.  
  
 Chcete-li ukončit relaci profilování, ukončete cílovou aplikaci a explicitně vypněte profiler. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
## <a name="start-the-profiling-session"></a>Spuštění relace profilování  
  
#### <a name="to-start-profiling-by-using-the-instrumentation-method"></a>Ke spuštění profilování pomocí metody instrumentace  
  
1.  Otevřete okno příkazového řádku. V případě potřeby přidejte adresář nástrojů profilování do proměnné prostředí PATH. Tato cesta není při instalaci přidána.  
  
2.  Použití **vsinstr –** nástroj pro generování instrumentovaného verzi cílové aplikace.  
  
3.  Inicializace proměnných prostředí profilování rozhraní .NET Framework. Typ:  
  
     **Vsperfclrenv – /traceon**  
  
4.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:trace output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: trasování** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:trace** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je vyžaduje jenom v případě, že je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník procesu, je uvedena ve **uživatelské jméno** sloupec **procesy** karty Správce úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Identifikátor relace, je uvedena ve **ID relace** sloupec **procesy** karty Správce úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění, které profileru se shromažďováním dat. pozastavena. Použití [/globalon](../profiling/globalon-and-globaloff.md) obnovit profilace.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Shromažďuje informace z čítače výkonu procesoru, který je uveden v `Config`. Čítač informace vkládá data, která se shromažďují v každé profilování události.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v samostatné (. *ETL*) souboru.|  
  
5.  Spusťte cílovou aplikaci z okna příkazového řádku.  
  
## <a name="control-data-collection"></a>Řízení shromažďování dat  
 Pokud cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do datového souboru profileru pomocí *VSPerfCmd.exe* možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno určeného ID vlákna (`TID`).|  
  
## <a name="end-the-profiling-session"></a>Ukončení relace profilování  
 Chcete-li ukončit relaci profilování, ukončete aplikaci, ve které běží instrumentovaná komponenta. Volání **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Zavřete cílová aplikace.  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – / vypnuto**  
  
## <a name="see-also"></a>Viz také:  
 [Profil samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)