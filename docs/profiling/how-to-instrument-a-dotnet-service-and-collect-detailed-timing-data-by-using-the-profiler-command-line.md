---
title: 'Postupy: Instrumentace služby rozhraní .NET a shromažďování podrobných dat časování pomocí příkazového řádku Profiler | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 0cd767e505af7e5d503695a1e7aea65dbfe62027
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747827"
---
# <a name="how-to-instrument-a-net-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line"></a>Postupy: Instrumentace služby .NET a shromažďování podrobných dat časování pomocí příkazového řádku profileru

Tento článek popisuje, jak pomocí Visual Studio nástroje příkazového řádku nástroje pro profilaci instrumentace služby rozhraní .NET Framework a shromažďování podrobných dat časování.

> [!NOTE]
> Metodou instrumentace nelze Profilovat službu, je-li nelze po spuštění počítače restartovat službu, například Služba spouštěná pouze spolu s operačním systémem.
>
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.
>
> Přidání dat interakce vrstvy do běhu profilování vyžaduje zvláštní procedury s nástroji pro profilaci příkazového řádku. Zobrazit [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).

Ke shromažďování podrobných dat časování pomocí metody instrumentace služby rozhraní .NET Framework, můžete použít [VSInstr.exe](../profiling/vsinstr.md) Nástroj generuje instrumentovanou verzi komponenty. Pak nahradíte neinstrumentovanou verzi služby instrumentovanou verzí, a ujistěte se, že je služba nastavena na Manuální spuštění. Můžete použít [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k inicializaci globálních proměnných prostředí profilování a poté restartujte hostitelský počítač. Potom spusťte profiler.

Když je služba spuštěna, data o časování jsou automaticky shromažďována do datového souboru. Můžete pozastavit a obnovit sběr dat. během relace profilování.

Chcete-li ukončit relaci profilování, vypněte službu a explicitně vypněte profiler. Ve většině případů doporučujeme na konci relace vyčistit proměnné prostředí profilování.

## <a name="start-the-application-with-the-profiler"></a>Spuštění aplikace s profilerem

1. Otevřete okno příkazového řádku.

2. Použití **VSInstr** Nástroj generuje instrumentovanou verzi binárního souboru služby.

3. Nahraďte původní binární soubor instrumentovanou verzí. Ve Windows správce řízení služeb, ujistěte se, že služby Typ spouštění je nastaven na ručně.

4. Inicializace proměnných prostředí profilování rozhraní .NET Framework. Zadejte:

     **VSPerfClrEnv /globaltraceon**

5. Restartujte počítač.

6. Otevřete okno příkazového řádku.

7. Spusťte profiler. Zadejte:

     **VSPerfCmd /start:trace /output:** `OutputFile` [`Options`]

   - [/Start](../profiling/start.md) **: trasování** možnost inicializuje profiler.

   - [/Output](../profiling/output.md) **:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění dat profilování (. *Vsp*) soubor.

     Můžete použít některou z následujících možností s **/start:trace** možnost.

     > [!NOTE]
     > **/User** a **/crosssession** možnosti jsou obvykle vyžadovány pro profilovací služby.

     | Možnost | Popis |
     | - | - |
     | [/ User](../profiling/user-vsperfcmd.md) **:** [`Domain` **\\** ]`UserName` | Určuje doménu a uživatelské jméno účtu vlastnícího profilovaný proces. Tato možnost je vyžadována, pouze pokud je proces spuštěn pod jiným než přihlášeným uživatelem. Vlastník procesu je uveden v **uživatelské jméno** sloupec **procesy** karty ve Správci úloh Windows. |
     | [/ crosssession](../profiling/crosssession.md) | Umožňuje profilování procesů v jiných relacích. Tato možnost je vyžadována, pokud je aplikace spuštěna v jiné relaci. ID je uvedeno v relaci **ID relace** sloupec na **procesy** karty ve Správci úloh Windows. **Protokolovacímu** může být zadán jako zkratka pro **/crosssession**. |
     | [/waitstart](../profiling/waitstart.md)[ **:** `Interval`] | Určuje počet sekund čekání na inicializaci předtím, než je vrácena chyba profileru. Pokud `Interval` není zadán, čeká profiler neomezeně dlouho. Ve výchozím nastavení **/start** vrátí hodnotu okamžitě. |
     | [/globaloff](../profiling/globalon-and-globaloff.md) | Chcete-li spustit profiler s shromažďování dat pozastaveno, přidejte **/globaloff** umožňuje **/start** příkazového řádku. Použití **globalon** obnovu profilování provedete. |
     | [/ Čítač](../profiling/counter.md) **:** `Config` | Shromažďuje informace z čítače výkonu procesoru zadaného v konfiguraci. Informace čítače se přidají do dat shromážděných při každé události profilování. |
     | [/wincounter](../profiling/wincounter.md) **:** `WinCounterPath` | Určuje čítač výkonu Windows má být shromážděn během profilování. |
     | [/automark](../profiling/automark.md) **:** `Interval` | Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500 ms. |
     | [/Events](../profiling/events-vsperfcmd.md) **:** `Config` | Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (. *ETL*) soubor. |

8. Spusťte službu z modulu snap-in Správce řízení služeb Windows.

## <a name="control-data-collection"></a>Řízení shromažďování dat

Pokud je služba spuštěna, můžete použít *VSPerfCmd.exe* možnosti spuštění a zastavení zápisu dat do datového souboru profilování. Řízení sběru dat umožňuje shromažďovat data pro určitou část provádění programu, například spouštění či ukončování služby.

- Následující páry **VSPerfCmd** možností spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví ( **/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí ( **/processon**) nebo zastaví ( **/processoff**) sběr dat pro proces určený identifikátorem procesu (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí ( **/threadon**) nebo zastaví ( **/threadoff**) sběr dat pro vlákno určené pomocí ID vlákna (`TID`).|

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování

Chcete-li ukončit relaci profilování, zastavte službu, která je spuštěna instrumentovaná komponenta a následně zavolat **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost profiler vypne a uzavře soubor dat profilování. **VSPerfClrEnv /globaloff** příkaz vymaže proměnné prostředí profilování.

Po restartování počítače-li použít nové nastavení prostředí.

1. Zastavte službu ze Správce řízení služeb.

2. Vypněte profiler. Typ:

     **/ Shutdown VSPerfCmd**

3. Po dokončení veškerého profilování vyčistěte proměnné prostředí profilování. Zadejte:

     **Vsperfclrenv – /globaloff**

4. Nahraďte instrumentovaný modul původní. V případě potřeby znovu nakonfigurujte typ spouštění služby.

5. Restartujte počítač.

## <a name="see-also"></a>Viz také:

[Profil služby](../profiling/command-line-profiling-of-services.md)
[zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)
