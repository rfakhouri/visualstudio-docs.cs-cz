---
title: 'Postupy: připojení profileru k webové aplikaci ASP.NET ke shromažďování dat paměti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: d608f85a-41ae-4ca7-85e6-b96624dbc83c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 0cd63358182c1e2e529bad02f372a6db8891652b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line"></a>Postupy: Připojení profileru k webové aplikaci ASP.NET ke shromažďování dat paměti pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikaci a shromažďování dat o počtu a velikosti přidělení paměti rozhraní .NET Framework. Může taky shromažďovat data o dobu trvání objektů paměti rozhraní .NET Framework.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Ke shromažďování dat výkonu z [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, je nutné použít [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k chybě při inicializaci příslušné proměnné prostředí v počítači, který je hostitelem [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Pak musíte restartovat počítač nakonfigurovat webový server pro vytváření profilů.  
  
 Pak použijete [VSPerfCmd.exe](../profiling/vsperfcmd.md) nástroj pro připojení profileru k [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces, který je hostitelem webové stránky. Po připojení profileru k aplikaci, můžete pozastavit a obnovit data kolekce.  
  
 K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
## <a name="attaching-the-profiler"></a>Připojení profileru  
  
#### <a name="to-attach-the-profiler-to-an-aspnet-web-application"></a>Chcete-li připojení profileru k webové aplikaci ASP.NET  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Inicializujte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv –** {**/globalsamplegc** &#124; **/globalsamplegclife**} [**/samplelineoff**]  
  
    -   Možnosti **/globalsamplegc** a **/globalsamplegclife** zadejte typ shromažďování dat paměti.  
  
         Zadejte pouze jeden z následujících možností.  
  
        |Možnost|Popis|  
        |------------|-----------------|  
        |**/globalsamplegc**|Umožňuje shromažďování dat o přidělení paměti.|  
        |**/globalsamplegclife**|Umožňuje shromažďování dat přidělování paměti a životnosti objektů.|  
  
    -   Možnost **/samplelineoff** zakáže přiřazení shromážděná data do konkrétního zdroje řádků kódu. Pokud je tato možnost zadána, je přiřazen data na úrovni funkce.  
  
3.  Restartujte počítač k nastavení novou konfiguraci prostředí.  
  
4.  Otevřete okno příkazového řádku. V případě potřeby nastavte profileru proměnné prostředí path.  
  
5.  Spusťte profileru. Typ:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: Ukázka**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]      
  
    -   **/Start:sample** možnost inicializuje profileru.  
  
    -   **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro aplikace ASP.NET.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Identifikátor relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/waitstart](../profiling/waitstart.md) [**:**`Interval`]|Určuje počet sekund pro čekání profileru k chybě při inicializaci předtím, než vrátí chybu. Pokud `Interval` není zadán, profileru čeká neomezenou dobu zaseknout. Ve výchozím nastavení **/start** vrátí okamžitě.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
6.  Spuštění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace v obvyklým způsobem.  
  
7.  Připojení profileru k [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces. Typ:  
  
     **VSPerfCmd**[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]    
  
    -   ID procesu `(PID)` Určuje ID procesu nebo názvu procesu [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
    -   **/targetclr:** `Version` určuje verzí common language runtime (CLR) má profil při načtení více než jednu verzi modulu runtime v aplikaci.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do datového souboru profileru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí `PID`.|  
    |**/ připojit:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;:`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, který je určen podle ID procesu nebo název procesu. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, musí být profileru odpojit od webové aplikace. Můžete zastavit shromažďování dat z aplikace, která je profilovaným pomocí metody vzorkování restartováním [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovních procesů nebo voláním **VSPerfCmd / detach** možnost. Potom zavolejte **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí, ale konfigurace systému není resetovat, dokud se počítač restartuje.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jeden z následujících kroků k odpojení profileru z cílová aplikace:  
  
    -   Typ **VSPerfCmd** [/ odpojit](../profiling/detach.md)  
  
         -nebo-  
  
    -   Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces. Typ:  
  
     **Příkaz IISReset/stop**  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfcmd – /globaloff**  
  
4.  Restartujte počítač. V případě potřeby restartování Internetové informační služby (IIS). Typ:  
  
     **Příkaz IISReset/Start**  
  
## <a name="see-also"></a>Viz také  
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)