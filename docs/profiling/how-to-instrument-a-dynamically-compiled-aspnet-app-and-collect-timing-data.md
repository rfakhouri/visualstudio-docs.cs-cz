---
title: 'Postupy: instrumentace dynamicky kompilované webové aplikace a shromažďování podrobných dat profileru časování pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 6be68c781b0117bca9ff895f0ecf62d97858a0a3
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line"></a>Postupy: Instrumentace dynamicky kompilované webové aplikace ASP.NET a shromažďování podrobných dat časování pomocí příkazového řádku profileru

Toto téma popisuje postup použití nástroje příkazového řádku Visual Studio Tools profilace ke shromažďování podrobných dat časování pro dynamicky kompilované [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace pomocí metoda profilování instrumentace.

> [!NOTE]
> Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

Ke shromažďování dat výkonu z [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace upravit soubor web.config aplikace cíl povolit [VSInstr.exe](../profiling/vsinstr.md) nástroj, který instrumentace dynamicky kompilované aplikace soubory. Pak použijete [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj na webovém serveru povolit profilace nastavit příslušné proměnné prostředí a pak restartujte počítač.

Spusťte profileru a pak spusťte cílová aplikace. Při profileru je připojen k aplikaci, můžete pozastavit a obnovit data kolekce. Po dokončení profilace, zavře se aplikace, zavřete pracovního procesu Internetové informační služby (IIS) a poté vypněte profileru. Po dokončení profilování práci v souboru web.config a webový server obnovte do původního stavu.

## <a name="configuring-the-aspnet-web-application-and-the-web-server"></a>Konfigurace webové aplikace a webový server

1. Upravte soubor web.config cílová aplikace. V tématu [postupy: Úprava souborů Web.Config za účelem instrumentace a profilování dynamicky kompilovaných webových aplikací ASP.NET](../profiling/how-to-modify-web-config-files-to-instrument-dynamically-compiled-aspnet-apps.md).

2. Otevřete okno příkazového řádku.

3. Inicializujte profilování proměnné prostředí. Typ:

     **Vsperfclrenv – /globaltraceon**

    - **/globaltraceon** umožňuje profilace pomocí metody instrumentace.

4. Restartujte počítač.

## <a name="running-the-profiling-session"></a>Spuštění relace profilování

1. Otevřete okno příkazového řádku.

2. Spusťte profileru. Typ:

     **VSPerfCmd**[/start](../profiling/start.md) **: trasování**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]

    - **/Start:trace** možnost inicializuje profileru.

    - **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).

     Můžete použít některou z následujících možností s **/start:trace** možnost.

    > [!NOTE]
    > **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro aplikace ASP.NET.

    |Možnost|Popis|
    |------------|-----------------|
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Identifikátor relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění, které profileru se shromažďováním dat. pozastavena. Použití [/globalon](../profiling/globalon-and-globaloff.md) obnovit profilace.|
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Shromažďuje informace z čítače výkonu procesoru, který je uveden v `Config`. Čítač informace vkládá data, která se shromažďují v každé profilování události.|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|

3. Spuštění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace v obvyklým způsobem.

## <a name="controlling-data-collection"></a>Řízení shromažďování dat

Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do datového souboru profileru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.

- Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno určeného ID vlákna (`TID`).|

- Můžete také **VSPerfCmd.exe**[/označit](../profiling/mark.md) možnost vložit do datového souboru profilování značky. **/Označit** příkaz přidá identifikátor, časové razítko a volitelné uživatelem definované textový řetězec. Značky lze použít k filtrování dat v zobrazení dat a sestav profileru.

## <a name="ending-the-profiling-session"></a>Ukončení relace profilování

K ukončení relace profilování, zavřete cíl [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, resetujte IIS zastavit proces PROFILOVANÉHO, a poté vypněte profileru.

1. Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace.

2. Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces resetováním Internetové informační služby (IIS). Typ:

     **Příkaz IISReset/stop**

3. Vypněte profileru. Typ:

     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)

4. Restartujte službu IIS. Typ:

     **Příkaz IISReset/Start**

## <a name="restoring-the-application-and-computer-configuration"></a>Obnovení konfigurace aplikace a počítače

Po dokončení všech profilace nahraďte v souboru web.config, vymažte profilování proměnné prostředí a restartujte počítač k obnovení serveru a aplikace na stavy, které se nacházely v před profilace.

1. V souboru web.config nahraďte kopií původního souboru.

2. Zrušte profilování proměnné prostředí. Typ:

     **Vsperfcmd – /globaloff**

3. Restartujte počítač.

## <a name="see-also"></a>Viz také

[Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)  
[Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)