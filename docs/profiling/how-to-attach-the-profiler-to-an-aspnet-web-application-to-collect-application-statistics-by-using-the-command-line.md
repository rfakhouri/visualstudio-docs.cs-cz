---
title: 'Postupy: připojení profileru k webové aplikaci ASP.NET ke shromažďování statistik aplikace pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3725ddbe-ce91-4469-991e-8c5ed048c618
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: a916e1d3410957a3f03c82436dee6f84bd57726b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line"></a>Postupy: Připojení profileru k webové aplikaci ASP.NET ke shromažďování statistik aplikace pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k webové aplikaci ASP.NET a shromažďování statistik výkonu pomocí metody vzorkování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Přidání dat interakce vrstev pro spuštění profilování vyžaduje konkrétní postupy s příkazového řádku nástroje pro profilaci. V tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
>   
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Ke shromažďování dat výkonu z webové aplikace ASP.NET, je nutné inicializovat příslušné proměnné prostředí a je nutné restartovat počítač, který je hostitelem aplikace ASP.NET Web, nakonfigurovat webový server pro profilace.  
  
 Potom připojení profileru k pracovního procesu ASP.NET, který je hostitelem webové stránky. Po připojení profileru k aplikaci, můžete pozastavit a obnovit data kolekce.  
  
 K ukončení relace profilování, musí být profileru odpojit od PROFILOVANÉHO aplikace a profileru musí být explicitně vypnuté. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
## <a name="starting-the-profiler-and-attaching-to-an-aspnet-web-application"></a>Spouštění profileru a připojení k webové aplikaci ASP.NET  
  
#### <a name="to-attach-the-profiler-to-an-aspnet-web-application"></a>Chcete-li připojení profileru k webové aplikaci ASP.NET  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Inicializujte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – /globalsampleon** [**/samplelineoff**]  
  
    -   **/globalsampleon** umožňuje vzorkování.  
  
    -   **/samplelineoff** zakáže přiřazení shromážděná data do konkrétního zdroje řádků kódu. Pokud je tato možnost zadána, je přiřazen data jenom k funkcím.  
  
3.  Restartujte počítač.  
  
4.  Spusťte profileru. Typ:**VSPerfCmd** [/start](../profiling/start.md)**: Ukázka** [/výstup](../profiling/output.md)**:**`OutputFile`[`Options`]  
  
    -   **/Start:sample** možnost inicializuje profileru.  
  
    -   **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro aplikace ASP.NET.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Identifikátor relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
5.  Spuštění aplikace technologie ASP.NET v obvyklým způsobem.  
  
6.  Připojení profileru k pracovního procesu technologie ASP.NET. Typ:**VSPerfCmd** [/ připojit](../profiling/attach.md)**:**{`PID`&#124;`ProcName`} [`Sample Event`] [[/targetclr](../profiling/targetclr.md) **:**`Version`]  
  
    -   `PID` Určuje Identifikátor procesu pracovního procesu ASP.NET; `ProcName` Určuje název pracovní proces. ID procesu a názvy všech spuštěných procesů můžete zobrazit ve Správci úloh systému Windows.  
  
    -   Ve výchozím nastavení, data výkonu vzorkovat hodin každých 10 000 000-zastavit procesoru cykly. Toto je přibližně 100krát za sekundu na 1GH procesoru. Můžete zadat jednu z následujících **VSPerfCmd** možnosti změnit interval cyklus hodiny, nebo zadejte jiný vzorkování událostí.  
  
    |Událost vzorku|Popis|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Interval vzorkování se změní na počet cyklů-Zastavit hodiny, které jsou určené `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Změny událostí vzorkování chyb stránek. Pokud `Interval` je zadané, nastaví počet chyb stránek mezi vzorky. Výchozí hodnota je 10.|  
    |[/ sys](../profiling/sys-vsperfcmd.md)[`:``Interval`]|Změny událostí vzorkování systémová volání z procesu s jádrem operačního systému (syscalls). Pokud `Interval` je zadané, nastaví počet volání mezi vzorky. Výchozí hodnota je 10.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Změny událostí vzorkování a intervalu čítače výkonu procesoru a interval, který jsou určené v `Config`.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Určuje verzi common language runtime (CLR) profilu při načtení více než jednu verzi modulu runtime v aplikaci.|  
  
    -   **targetclr:** `Version` Určuje verzi modulu CLR do profilu při načtení více než jednu verzi modulu runtime v aplikaci. Volitelné.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` **/processoff:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, který je zadán `PID`.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí `PID` nebo název procesu (Nazev_procedury). **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, zavřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci a potom pomocí Internetové informační služby (IIS) **IISReset** příkaz zavřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces. Volání **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru.  
  
 **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí. Musíte restartovat počítač pro použití nového nastavení prostředí.  
  
 **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí, ale konfigurace systému není resetovat, dokud se počítač restartuje.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jednu z následujících způsobů odpojit profileru z cílová aplikace:  
  
    -   Typ **VSPerfCmd / odpojit**  
  
         -nebo-  
  
    -   Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces.  
  
2.  Vypněte profileru. Typ:**VSPerfCmd**  [ /Shutdown](../profiling/shutdown.md)  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfcmd – /globaloff**  
  
4.  Restartujte počítač.  
  
## <a name="see-also"></a>Viz také  
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)