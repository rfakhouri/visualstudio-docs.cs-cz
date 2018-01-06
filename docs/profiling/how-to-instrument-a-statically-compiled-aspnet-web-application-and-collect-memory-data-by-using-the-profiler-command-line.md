---
title: "Postupy: instrumentace staticky kompilované ASP.NET webové aplikace a shromažďování dat paměti pomocí příkazového řádku profileru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea1dcb7c-1dc3-49ff-9418-8795b5b3d3bc
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5a35d15fc4d0859ca005cff96aab51f9c5fbd277
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line"></a>Postupy: Instrumentace staticky kompilované webové aplikace ASP.NET a shromažďování dat paměti pomocí příkazového řádku profileru
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci k instrumentaci předem kompilovaném [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] součást webové nebo webu a shromažďování přidělení paměti .NET, doba života objektu a podrobných dat časování.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. V 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Ke shromažďování dat z [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] součást webové pomocí metody instrumentace, můžete použít [VSInstr.exe](../profiling/vsinstr.md) nástroj pro generování instrumentovaného verzi komponentu. Na počítači, který je hostitelem součásti nahraďte-instrumentovány verze součásti instrumentovaného verze. Pak použijete [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k inicializaci globální profilování proměnné prostředí a restartovat hostitelský počítač. Potom je nutné spustit profileru.  
  
 Po provedení komponentu instrumentovaného časování data jsou shromažďována automaticky do datového souboru. Můžete pozastavit a obnovit shromažďování dat během relace profilování.  
  
 K ukončení relace profilování, zavřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces, který je hostitelem součásti a poté explicitně vypněte profileru. Ve většině případů doporučujeme vymazání na konci relace profilování proměnné prostředí.  
  
## <a name="starting-to-profile"></a>Spuštění profilu  
  
#### <a name="to-instrument-an-aspnet-web-component-and-start-profiling"></a>Spustit profilování a instrumentace rozhraní ASP.NET Web součásti  
  
1.  Použití **vsinstr –** nástroj pro generování instrumentovaného verzi cílové aplikace. V případě potřeby nahraďte binární soubory aplikace v hostitelském počítači ASP.NET instrumentované binární soubory.  
  
2.  Otevřete okno příkazového řádku  
  
3.  Inicializujte .NET profilace proměnné prostředí. V okně příkazového řádku zadejte:  
  
     **Vsperfclrenv – /globaltracegc**  
  
     -nebo-  
  
     **Vsperfclrenv – /globaltracegclife**  
  
    -   **/globaltracegc** shromažďuje přidělení paměti .NET a dat časování.  
  
    -   **/globaltracegclife** přidělení paměti .NET shromažďuje, doba života objektu a podrobných dat časování.  
  
4.  Restartujte počítač.  
  
5.  Otevřete okno příkazového řádku.  
  
6.  Spusťte profileru. V okně příkazového řádku zadejte:  
  
     **VSPerfCmd /start:trace output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: trasování** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile`Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:trace** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro aplikace ASP.NET.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje nepovinné domény a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel, který se liší od přihlášeného uživatele. Název je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích. Tato možnost je povinná, pokud je aplikace spuštěna v jiné relaci. Id relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:**`WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:**`Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:**`Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění profileru se shromažďování dat pozastavena, přidejte **/globaloff** možnost k **/start** příkazového řádku. Použití **/globalon** obnovit profilace.|  
  
7.  Otevřete web, který obsahuje komponentu instrumentované.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**`PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:**`TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno určeného ID vlákna (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, zavřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci a potom pomocí Internetové informační služby (IIS) **IISReset** příkaz zavřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces. Volání **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí. Musíte restartovat počítač pro použití nového nastavení prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace.  
  
2.  Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces. Typ:  
  
     **Příkaz IISReset/stop**  
  
3.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
4.  (Volitelné). Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfcmd – /globaloff**  
  
5.  Restartujte počítač. V případě potřeby restartujte službu IIS. Typ:  
  
     **Příkaz IISReset/Start**  
  
## <a name="see-also"></a>Viz také  
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)