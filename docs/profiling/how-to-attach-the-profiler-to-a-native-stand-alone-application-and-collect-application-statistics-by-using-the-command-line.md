---
title: 'Postupy: připojení profileru k nativní samostatné aplikaci a shromažďování statistik aplikace pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: df44fe42-281b-4398-b3fc-277b62ae41f1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: c9ef8415aaa9a5004528841c2fc9c466a8374459
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line"></a>Postupy: Připojení profileru k nativní samostatné aplikaci a shromažďování statistik aplikace pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci k připojení profileru k samostatné spuštění nativní (klientskou) aplikaci a shromažďování statistik výkonu pomocí metody vzorkování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Po připojení profileru k aplikaci, můžete pozastavit a obnovit data kolekce. K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté.  
  
## <a name="attach-the-profiler"></a>Připojení profileru  
 Chcete-li připojení profileru k cílové aplikace pomocí profileru, použijte **VSPerfCmd a spustit** a **/ připojit** možnosti inicializovat profileru a připojení k cílové aplikaci. Můžete zadat **/start** a **/ připojit** a jejich odpovídající možnosti na jednoho příkazového řádku. Můžete také přidat **/globaloff** možnost pozastavit shromažďování dat na začátku cílová aplikace. Pak použijete **/globalon** zahájíte shromažďovat data.  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Chcete-li připojení profileru k spuštěné aplikace rozhraní .NET Framework  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:sample output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: Ukázka** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je vyžaduje jenom v případě, že je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Identifikátor relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
3.  Připojení profileru k cílové aplikaci. Typ:  
  
     **VSPerfCmd**[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [`Sample Event`]    
  
     `PID` Určuje ID procesu cílová aplikace. `ProcessName` Určuje název procesu. Všimněte si, že pokud zadáte `ProcessName` a více procesy, které mají stejný název běží, výsledky mohou být nepředvídatelné. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
     Ve výchozím nastavení, data výkonu vzorkovat hodin každých 10 000 000-zastavit procesoru cykly. Toto je přibližně 100krát každou sekundu 1GH procesoru. Můžete zadat jednu z následujících možností, chcete-li změnit interval cyklus hodin nebo k zadání různých vzorkování událostí.  
  
    |Událost vzorku|Popis|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Interval vzorkování se změní na počet cyklů-Zastavit hodiny, které jsou určené `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Změny událostí vzorkování chyb stránek. Pokud `Interval` je zadané, nastaví počet chyb stránek mezi vzorky. Výchozí hodnota je 10.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Změny událostí vzorkování systémová volání z procesu s jádrem operačního systému (syscalls). Pokud `Interval` je zadané, nastaví počet volání mezi vzorky. Výchozí hodnota je 10.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Změny událostí vzorkování a intervalu čítač výkonu procesoru a interval, který je uveden v `Config`.|  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když cílová aplikace běží, můžete VSPerfCmd.exe možnosti spuštění a zastavení zápisu dat do datového souboru profileru. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, například spuštění nebo ukončení aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, který je zadán `PID`.|  
    |[/ připojit](../profiling/attach.md) **:** `PID` [/ odpojit](../profiling/detach.md)|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí `PID`. **/ detach** zastaví sběr dat pro všechny procesy.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, musí být profileru odpojit od všech PROFILOVANÉHO procesů a profileru musí být explicitně vypnuté. Můžete odpojit profileru z aplikace, která byla profilovaným pomocí metody vzorkování ukončením aplikace nebo voláním **VSPerfCmd / detach** možnost. Potom zavolejte **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jeden z následujících kroků k odpojení profileru z cílové aplikace.  
  
    -   Typ **VSPerfCmd / odpojit**  
  
         -nebo-  
  
    -   Zavřete cílová aplikace.  
  
2.  Vypněte profileru. Typ:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – / vypnuto**  
  
## <a name="see-also"></a>Viz také  
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)