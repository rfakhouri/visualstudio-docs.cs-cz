---
title: 'Profiler příkazový řádek: Instrumentace dynamické aplikace ASP.NET a získejte data časování'
ms.date: 11/04/2016
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 656cceea8cfc76d9c4865b5a2a792993e3f90f15
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2019
ms.locfileid: "67032001"
---
# <a name="how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler-by-using-the-command-line"></a>Postupy: Instrumentace dynamicky kompilované webové aplikace ASP.NET a shromažďování podrobných dat časování pomocí příkazového řádku profileru

Tento článek popisuje, jak používat Visual Studio nástroje příkazového řádku nástroje pro profilaci ke shromažďování podrobných dat časování pro dynamicky kompilovaných [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace s použitím metoda profilace instrumentace.

> [!NOTE]
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.

Ke shromažďování dat výkonu z [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, můžete upravit *web.config* soubor cílové aplikace umožňující [VSInstr.exe](../profiling/vsinstr.md) nástroj instrumentace dynamicky kompilované soubory aplikace. Pak použijete [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroje nastavit příslušné proměnné prostředí na webový server a povolit profilaci a pak restartujte počítač.

Spusťte profiler a pak spusťte cílovou aplikaci. Zatímco je profiler připojen k aplikaci, lze pozastavit a obnovit sběr dat. Po dokončení profilování, ukončete aplikaci, zavřete pracovní proces služby IIS (Internetová informační služba) a poté vypněte profiler. Po dokončení profilování práci, obnovte *web.config* souboru a webový server do původního stavu.

## <a name="configure-the-aspnet-web-application-and-the-web-server"></a>Konfigurace webové aplikace ASP.NET a webového serveru

1. Upravit *web.config* soubor cílové aplikace. Zobrazit [jak: Úprava souborů web.config za účelem instrumentace a profilování dynamicky kompilovaných webových aplikací ASP.NET](../profiling/how-to-modify-web-config-files-to-instrument-dynamically-compiled-aspnet-apps.md).

2. Otevřete okno příkazového řádku.

3. Inicializujte proměnné prostředí profilování. Zadejte:

     **VSPerfClrEnv /globaltraceon**

    - **/globaltraceon** povolí profilaci pomocí metody instrumentace.

4. Restartujte počítač.

## <a name="run-the-profiling-session"></a>Spuštění relace profilování

1. Otevřete okno příkazového řádku.

2. Spusťte profiler. Zadejte:

     **Nástroj VSPerfCmd**[/start](../profiling/start.md) **: trasování**[/output](../profiling/output.md) **:** `OutputFile` [`Options`]

   - **/Start:trace** možnost inicializuje profiler.

   - **/Output:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění dat profilování (. *Vsp*) soubor.

     Můžete použít některý z těchto možností s **/start:trace** možnost.

     > [!NOTE]
     > **/User** a **/crosssession** možnosti jsou obvykle vyžadovány pro aplikace ASP.NET.

     | Možnost | Popis |
     | - | - |
     | [/ User](../profiling/user-vsperfcmd.md) **:** [`Domain` **\\** ]`UserName` | Určuje doménu a uživatelské jméno účtu vlastnícího pracovní proces ASP.NET. Tato možnost je vyžadována, pokud je proces spuštěn pod jiným než přihlášeným uživatelem. Vlastník procesu je uveden v **uživatelské jméno** sloupec **procesy** karty ve Správci úloh Windows. |
     | [/ crosssession](../profiling/crosssession.md) | Umožňuje profilování procesů v jiných přihlašovacích relacích. Tato možnost je vyžadována, pokud je aplikace ASP.NET spuštěna v jiné relaci. Identifikátor relace je uveden v **ID relace** sloupec **procesy** karty ve Správci úloh Windows. **Protokolovacímu** může být zadán jako zkratka pro **/crosssession**. |
     | [/globaloff](../profiling/globalon-and-globaloff.md) | Spuštění, které se shromažďováním dat profileru pozastaveno. Použití [globalon](../profiling/globalon-and-globaloff.md) obnovu profilování provedete. |
     | [/ Čítač](../profiling/counter.md) **:** `Config` | Shromažďuje informace z čítače výkonu procesoru, který je zadán v `Config`. Informace čítače se přidají do dat shromážděných při každé události profilování. |
     | [/wincounter](../profiling/wincounter.md) **:** `WinCounterPath` | Určuje čítač výkonu Windows má být shromážděn během profilování. |
     | [/automark](../profiling/automark.md) **:** `Interval` | Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500 ms. |
     | [/Events](../profiling/events-vsperfcmd.md) **:** `Config` | Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (. *ETL*) soubor. |

3. Spustit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci obvyklým způsobem.

## <a name="control-data-collection"></a>Řízení shromažďování dat

Dokud je cílová aplikace spuštěna, lze sběr dat řídit spouštěním či pozastavováním zápisu dat do datového souboru profilování pomocí *VSPerfCmd.exe* možnosti. Řízení sběru dat umožňuje shromažďovat data pro určitou část provádění programu, například spouštění či ukončování aplikace.

- Následující páry možností spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví ( **/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí ( **/processon**) nebo zastaví ( **/processoff**) sběr dat pro proces určený identifikátorem procesu (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí ( **/threadon**) nebo zastaví ( **/threadoff**) sběr dat pro vlákno určené pomocí ID vlákna (`TID`).|

- Můžete také použít **VSPerfCmd.exe**[/mark](../profiling/mark.md) možnost k vložení profilovací značky do datového souboru. **/Mark** příkaz přidá identifikátor, časové razítko a volitelný uživatelem definovaný textový řetězec. Značky lze použít k filtrování dat v zobrazení data a sestavy profileru.

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování

Chcete-li ukončit relaci profilování, zavřete cíl [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, restartujte službu IIS zastavte profilovaných procesů a poté vypněte profiler.

1. Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci.

2. Zavřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces resetováním Internetové informační služby (IIS). Zadejte:

     **Příkaz IISReset/stop**

3. Vypněte profiler. Typ:

     **Nástroj VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)

4. Restartujte službu IIS. Zadejte:

     **Příkaz IISReset/Start**

## <a name="restore-the-application-and-computer-configuration"></a>Obnovit konfiguraci aplikace a počítače

Po dokončení veškerého profilování nahradit *web.config* souboru, vyčistěte proměnné prostředí pro profilování a restartujte počítač a obnovit stavy, které se nacházely před profilace aplikace a serveru.

1. Nahradit *web.config* souboru kopií původního souboru.

2. Vyčistěte proměnné prostředí profilování. Zadejte:

     **Nástroj VSPerfCmd /globaloff**

3. Restartujte počítač.

## <a name="see-also"></a>Viz také:

[Profilovat webové aplikace ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
[zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)