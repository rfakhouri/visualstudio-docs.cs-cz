---
title: "Postupy: připojení profileru ke službě .NET ke shromažďování dat paměti pomocí příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aeac39af-ad99-479f-aa36-4104356ca512
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0b16ef90f0babc8f9acd1999fd474bd4d122f523
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-attach-the-profiler-to-a-net-service-to-collect-memory-data-by-using-the-command-line"></a>Postupy: Připojení profileru ke službě .NET ke shromažďování dat paměti pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] služby a shromažďování dat paměti. Můžete shromáždit data o počtu a velikosti přidělování paměti a může taky shromažďovat data o dobu trvání paměti objektů.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. V 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Ke shromažďování dat paměti z [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] služby, můžete použít [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k chybě při inicializaci příslušné proměnné prostředí v počítači, který hostuje službu. Počítač musí restartovat ho nakonfigurovat pro použití profilů.  
  
 Pak použijete [VSPerfCmd](../profiling/vsperfcmd.md) nástroj pro připojení profileru k procesu služby. Při profileru je připojen ke službě, můžete pozastavit a obnovit data kolekce.  
  
 Chcete-li ukončit relaci profilování, musí být profiler odpojen od služby a poté explicitně ukončen. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
## <a name="attaching-the-profiler"></a>Připojení profileru  
  
#### <a name="to-attach-the-profiler-to-a-net-framework-service"></a>Chcete-li připojení profileru ke službě rozhraní .NET Framework  
  
1.  V případě potřeby nainstalujte službu.  
  
2.  Otevřete okno příkazového řádku.  
  
3.  Inicializujte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv –** {**/globalsamplegc /globalsamplegclife**} [**/samplelineoff**]  
  
    -   Možnosti **/globalsamplegclife** a **/globalsamplegclife** zadejte typ shromažďování dat paměti. Zadejte pouze jeden z následujících možností.  
  
     **/globalsamplegc**  
     Umožňuje shromažďování dat o přidělení paměti.  
  
     **/globalsamplegclife**  
     Umožňuje shromažďování dat přidělování paměti a životnosti objektů.  
  
    -   **/Samplelineoff** možnost zakáže shromažďování dat o zdrojovém kódu řádku číslo.  
  
4.  Restartujte počítač k nastavení novou konfiguraci prostředí.  
  
5.  V případě potřeby spusťte službu.  
  
6.  Otevřete okno příkazového řádku. V případě potřeby přidejte cestu profileru do proměnné prostředí PATH.  
  
7.  Spusťte profileru. Typ:  
  
     **VSPerfCmd**[/start](../profiling/start.md) **: Ukázka**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]  
  
    -   **/Start:sample** možnost inicializuje profileru.  
  
    -   **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile`Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít jeden nebo více z následujících možností s **/start:sample** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro služby.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní proces. Tato možnost je povinná, pokud je proces spuštěný jako uživatel, než je přihlášený uživatel. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Id relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje nepovinné doména a uživatelské jméno přihlašovací účet, pod kterým je služba spuštěna. Přihlašovací účet je uvedena ve sloupci přihlášení jako služby ve správci řízení služby systému Windows.|  
    |[/crosssession &#124; cs](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
8.  Připojení profileru ke službě. Typ:  
  
     **VSPerfCmd**[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]  
  
    -   Zadejte buď ID procesu, nebo název procesu služby. ID procesu a názvy všech spuštěných procesů můžete zobrazit ve Správci úloh systému Windows.  
  
    -   **targetclr:** `Version` určuje verzí common language runtime (CLR) má profil při načtení více než jednu verzi modulu runtime v aplikaci. Volitelné.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když je služba spuštěná, můžete použít **VSPerfCmd.exe** možnosti zastavení a spuštění zápis dat do datového souboru profileru. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |**/ připojit:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí ID procesu nebo název procesu. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat z aplikace profilovaným pomocí metody vzorkování Probíhá zastavování služby, nebo volání **VSPerfCmd / detach** možnost. Potom zavolejte **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí, ale konfigurace systému není resetovat, dokud se počítač restartuje.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jednu z následujících způsobů odpojit profileru z cílová aplikace:  
  
    -   Zastavte službu.  
  
         -nebo-  
  
    -   Typ **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – /globaloff**  
  
4.  Restartujte počítač.  
  
## <a name="see-also"></a>Viz také  
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)