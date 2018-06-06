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
ms.openlocfilehash: b69e67bce9623c9b5b7a6fc943ace0f08ce2d7da
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815240"
---
# <a name="how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line"></a>Postupy: instrumentace dynamicky kompilované webové aplikace ASP.NET a shromažďování podrobných dat časování profileru pomocí příkazového řádku

Tento článek popisuje, jak pomocí nástroje příkazového řádku Visual Studio Tools profilace ke shromažďování podrobných dat časování pro dynamicky kompilované [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace pomocí metoda profilování instrumentace.

> [!NOTE]
> Nástroje příkazového řádku nástroje profilace jsou umístěné v *\Team Tools\Performance nástroje* podadresáři [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [zadejte cestu k nástroje příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

Ke shromažďování dat výkonu z [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, můžete změnit *web.config* souboru cílová aplikace povolit [VSInstr.exe](../profiling/vsinstr.md) nástroj, který instrumentace dynamicky kompilované soubory aplikace. Pak použijete [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj na webovém serveru povolit profilace nastavit příslušné proměnné prostředí a pak restartujte počítač.

Spusťte profileru a pak spusťte cílová aplikace. Při profileru je připojen k aplikaci, můžete pozastavit a obnovit data kolekce. Po dokončení profilace, zavře se aplikace, zavřete pracovního procesu Internetové informační služby (IIS) a poté vypněte profileru. Po dokončení profilování práci obnovit *web.config* souborový a webový server do původního stavu.

## <a name="configure-the-aspnet-web-application-and-the-web-server"></a>Konfigurace webové aplikace ASP.NET a webový server

1. Změnit *web.config* souboru cílová aplikace. V tématu [postupy: Úprava souborů web.config a instrumentace dynamicky kompilované webové aplikace ASP.NET profilu](../profiling/how-to-modify-web-config-files-to-instrument-dynamically-compiled-aspnet-apps.md).

2. Otevřete okno příkazového řádku.

3. Inicializujte profilování proměnné prostředí. Typ:

     **Vsperfclrenv – /globaltraceon**

    - **/globaltraceon** umožňuje profilace pomocí metody instrumentace.

4. Restartujte počítač.

## <a name="run-the-profiling-session"></a>Spuštění relace profilování

1. Otevřete okno příkazového řádku.

2. Spusťte profileru. Typ:

     **VSPerfCmd**[/start](../profiling/start.md) **: trasování**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]

    - **/Start:trace** možnost inicializuje profileru.

    - **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění data profilování (. *Vsp*) souboru.

     Můžete použít některou z následujících možností s **/start:trace** možnost.

    > [!NOTE]
    > **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro aplikace ASP.NET.

    |Možnost|Popis|
    |------------|-----------------|
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel než přihlášeného uživatele. Vlastník procesu, je uvedena ve **uživatelské jméno** sloupec **procesy** karty Správce úloh systému Windows.|
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Identifikátor relace, je uvedena ve **ID relace** sloupec **procesy** karty Správce úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění, které profileru se shromažďováním dat. pozastavena. Použití [/globalon](../profiling/globalon-and-globaloff.md) obnovit profilace.|
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Shromažďuje informace z čítače výkonu procesoru, který je uveden v `Config`. Čítač informace vkládá data, která se shromažďují v každé profilování události.|
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v samostatné (. *ETL*) souboru.|

3. Spuštění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace v obvyklým způsobem.

## <a name="control-data-collection"></a>Řízení shromažďování dat

Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do datového souboru profileru pomocí *VSPerfCmd.exe* možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.

- Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno určeného ID vlákna (`TID`).|

- Můžete také **VSPerfCmd.exe**[/označit](../profiling/mark.md) možnost vložit do datového souboru profilování značky. **/Označit** příkaz přidá identifikátor, časové razítko a volitelné uživatelem definované textový řetězec. Značky lze použít k filtrování dat v zobrazení dat a sestav profileru.

## <a name="end-the-profiling-session"></a>Ukončení relace profilování

K ukončení relace profilování, zavřete cíl [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, resetujte IIS zastavit proces PROFILOVANÉHO, a poté vypněte profileru.

1. Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace.

2. Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces resetováním Internetové informační služby (IIS). Typ:

     **Příkaz IISReset/stop**

3. Vypněte profileru. Typ:

     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)

4. Restartujte službu IIS. Typ:

     **Příkaz IISReset/Start**

## <a name="restore-the-application-and-computer-configuration"></a>Obnovit konfiguraci aplikace a počítače

Pokud jste vyplnili všechny profilace, nahraďte *web.config* souboru, zrušte profilování proměnné prostředí a restartujte počítač k obnovení serveru a aplikace na stavy, které se nacházely v před profilace.

1. Nahraďte *web.config* soubor s kopií původního souboru.

2. Zrušte profilování proměnné prostředí. Typ:

     **Vsperfcmd – /globaloff**

3. Restartujte počítač.

## <a name="see-also"></a>Viz také:

[Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)  
[Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)