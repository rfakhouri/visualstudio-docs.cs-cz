---
title: "Postupy: připojení profileru k samostatné aplikaci .NET Framework ke shromažďování dat paměti pomocí příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a869fa4-3c98-4e08-b5d9-f43523059f0e
caps.latest.revision: "33"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca6318b5280e2098858bdcf523a3131cf68b7c84
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line"></a>Postupy: Připojení profileru k samostatné aplikaci .NET Framework ke shromažďování dat paměti pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k aplikaci spuštěné samostatné (klient) rozhraní .NET Framework a shromažďování dat paměti.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Připojit k aplikaci .NET Framework a shromažďování paměti dat, je nutné použít [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k chybě při inicializaci příslušné proměnné prostředí před spuštěním cílové aplikace. Po připojení profileru k aplikaci, můžete použít **VSPerfCmd.exe** nástroj pro pozastavení a obnovení dat kolekce.  
  
 K ukončení relace profilování, musí být profileru odpojit od všech PROFILOVANÉHO procesů a profileru musí být explicitně vypnuté. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
## <a name="attaching-the-profiler"></a>Připojení profileru  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Chcete-li připojení profileru k spuštěné aplikace rozhraní .NET Framework  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Inicializujte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv –** {**/samplegc** &#124; **/samplegclife**} [**/samplelineoff**]  
  
    -   **/Samplegc** a **/samplegclife** možnosti určete, jestli ke shromažďování dat přidělení paměti pouze nebo shromažďovat přidělování paměti a životnosti objektů. Je třeba zadat pouze jednu možnost.  
  
        |Možnost|Popisy|  
        |------------|------------------|  
        |**/samplegc**|Shromažďujte pouze data přidělení paměti.|  
        |**/samplegclife**|Shromážděte přidělování paměti a životnosti objektů.|  
  
    -   **/Samplelineoff** možnost zakáže shromažďování dat o zdrojovém kódu řádku číslo.  
  
3.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:sample output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: Ukázka** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile`Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je vyžaduje jenom v případě, že je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession &#124; /cs](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích. Tato možnost je povinná, pokud je aplikace spuštěna v jiné relaci. Idenitifer relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
  
4.  V případě potřeby spusťte cílová aplikace typické způsobem.  
  
5.  Připojení profileru k cílové aplikaci. Typ:  
  
     **VSPerfCmd**[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]  
  
    -   `PID`Určuje ID procesu cílová aplikace. `ProcessName`Určuje název procesu. Všimněte si, že pokud zadáte `ProcessName` a více procesy, které mají stejný název běží, výsledky mohou být nepředvídatelné. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
    -   **/targetclr:** `Version` určuje verzí common language runtime (CLR) má profil při načtení více než jednu verzi modulu runtime v aplikaci. Volitelné.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Pokud cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, který je zadán `PID`.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, který je zadán `PID` nebo název procesu (Nazev_procedury). **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, musí být profileru odpojit od všech PROFILOVANÉHO procesů a profileru musí být explicitně vypnuté. Můžete odpojit profileru z aplikace, která byla profilovaným pomocí metody vzorkování ukončením aplikace nebo voláním **VSPerfCmd / detach** možnost. Potom zavolejte **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jeden z následujících kroků k odpojení profileru z cílová aplikace:  
  
    -   Typ **VSPerfCmd / odpojit**  
  
         -nebo-  
  
    -   Zavřete cílová aplikace.  
  
2.  Vypněte profileru. Typ:  
  
     **VSPerfCmd** [ /Shutdown  ](../profiling/shutdown.md)  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **VSPerfCmd / vypnuto**  
  
## <a name="see-also"></a>Viz také  
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)