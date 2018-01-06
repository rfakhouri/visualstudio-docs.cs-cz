---
title: "Postupy: připojení profileru k nativní službě ke shromažďování statistik aplikace pomocí příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f783817f-77a0-4eb8-985b-ec3b77eadc42
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b84efa68a82f857179f7cffb22d93455dd723078
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line"></a>Postupy: Připojení profileru k nativní službě ke shromažďování statistik aplikace pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci k připojení profileru k nativní službě a shromažďování statistik výkonu pomocí metody vzorkování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. V 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Při profileru je připojen ke službě, můžete pozastavit a obnovit data kolekce.  
  
 Chcete-li ukončit relaci profilování, musí být profiler odpojen od služby a poté explicitně ukončen.  
  
## <a name="starting-the-application-with-the-profiler"></a>Spouštění aplikace s Profilerem  
 Chcete-li připojení profileru k nativní službě, použijte **VSPerfCmd.exe**[/start](../profiling/start.md) a [/ připojit](../profiling/attach.md) možnosti inicializovat profileru a jeho připojení k cílové aplikaci. Můžete zadat **/start** a **/ připojit** a jejich odpovídající možnosti na jednoho příkazového řádku. Můžete také přidat [/globaloff](../profiling/globalon-and-globaloff.md) možnost pozastavit shromažďování dat na začátku cílová aplikace. Pak můžete použít [/globalon](../profiling/globalon-and-globaloff.md) zahájíte shromažďování dat.  
  
#### <a name="to-attach-the-profiler-to-a-native-service"></a>Chcete-li připojení profileru k nativní službě  
  
1.  V případě potřeby spusťte službu.  
  
2.  Otevřete okno příkazového řádku.  
  
3.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:sample**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]  
  
    -   **/Start:sample** možnost inicializuje profileru.  
  
    -   **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile`Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro služby.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je vyžaduje jenom v případě, že je proces spuštěný jako uživatel, než je přihlášený uživatel. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích. Tato možnost je povinná, pokud je aplikace spuštěna v jiné relaci. Id relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
4.  Připojení profileru ke službě. Typ:  
  
     **VSPerfCmd / připojit:** `PID` [`Sample Event`]  
  
     `PID`Určuje ID procesu cílová aplikace. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
     Ve výchozím nastavení, data výkonu vzorkovat hodin každých 10 000 000-zastavit procesoru cykly. Toto je přibližně jednou každých 10 sekund 1GH procesoru. Můžete zadat jednu z následujících možností změnit interval cyklus hodiny nebo zadejte jiný vzorkování událostí.  
  
    |Událost vzorku|Popis|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:**`Interval`|Změní interval vzorkování na počet nepřerušených hodinových cyklů určených parametrem `Interval`.|  
    |[/PF](../profiling/pf.md)[**:**`Interval`]|Změny událostí vzorkování chyb stránek. Pokud `Interval` je zadané, nastaví počet chyb stránek mezi vzorky. Výchozí hodnota je 10.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Změny událostí vzorkování systémová volání z procesu s jádrem operačního systému (syscalls). Pokud `Interval` je zadané, nastaví počet volání mezi vzorky. Výchozí hodnota je 10.|  
    |[/ Čítač](../profiling/counter.md) **:**`Config`|Změní událost a interval vzorkování na čítač výkonu a interval procesoru určený parametrem `Config`.|  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když cílová aplikace běží, můžete použít **VSPerfCmd.exe** možnosti spuštění a zastavení zápisu dat do datového souboru profileru. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |**/ připojit:** {`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces zadaný pomocí ID procesu nebo název procesu. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, profileru musí být odpojit od služby a poté explicitně vypněte. Můžete odpojit nativní služba, která je profilovaným pomocí metody vzorkování Probíhá zastavování služby, nebo volání **VSPerfCmd / detach** možnost. Potom zavolejte **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jednu z následujících způsobů odpojit profileru z cílová aplikace:  
  
    -   Zastavte službu.  
  
         -nebo-  
  
    -   Typ **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
## <a name="see-also"></a>Viz také  
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)   
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)