---
title: 'Profiler příkazový řádek: Instrumentace součásti .NET klienta, získání dat v čase'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b7dcc27b-45c6-4302-9552-6fa5b1e94b56
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ff23dd4995be70c9a34c95dbe744961b75de3e0c
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2019
ms.locfileid: "67032899"
---
# <a name="how-to-instrument-a-stand-alone-net-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line"></a>Postupy: Instrumentace samostatné součásti rozhraní .NET Framework a shromažďování dat časování s profilerem z příkazového řádku
Toto téma popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci k instrumentaci komponenty rozhraní .NET Framework, jako. *soubor exe* nebo. *Knihovna DLL* souboru a shromažďování podrobných dat časování.

> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).
>
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.
>
> Přidání dat interakce vrstvy do běhu profilování vyžaduje zvláštní procedury s nástroji pro profilaci příkazového řádku. Zobrazit [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).

 Ke shromažďování podrobných dat časování z komponenty rozhraní .NET Framework pomocí metody instrumentace, můžete použít [VSInstr.exe](../profiling/vsinstr.md) Nástroj generuje instrumentovanou verzi komponenty a [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k inicializaci proměnné prostředí profilování. Potom spusťte profiler.

 Po spuštění instrumentované komponenty jsou data časování jsou automaticky shromažďována do datového souboru. Můžete pozastavit a obnovit sběr dat. během relace profilování.

 Chcete-li ukončit relaci profilování, ukončete cílovou aplikaci a explicitně vypněte profiler. Ve většině případů doporučujeme na konci relace vyčistit proměnné prostředí profilování.

## <a name="start-the-profiling-session"></a>Spuštění relace profilování

#### <a name="to-start-profiling-by-using-the-instrumentation-method"></a>Spuštění profilování pomocí metody instrumentace

1. Otevřete okno příkazového řádku. V případě potřeby přidejte adresář nástrojů profilování do proměnné prostředí PATH. Tato cesta není při instalaci přidána.

2. Použití **VSInstr** Nástroj generuje instrumentovanou verzi cílové aplikace.

3. Inicializace proměnných prostředí profilování rozhraní .NET Framework. Zadejte:

    **VSPerfClrEnv /traceon**

4. Spusťte profiler. Zadejte:

    **VSPerfCmd /start:trace /output:** `OutputFile` [`Options`]

   - [/Start](../profiling/start.md) **: trasování** možnost inicializuje profiler.

   - [/Output](../profiling/output.md) **:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění souboru dat profilování (.vsp).

     Můžete použít některou z následujících možností s **/start:trace** možnost.

   | Možnost | Popis |
   | - | - |
   | [/ User](../profiling/user-vsperfcmd.md) **:** [`Domain` **\\** ]`UserName` | Určuje doménu a uživatelské jméno účtu vlastnícího profilovaný proces. Tato možnost je vyžadována, pouze pokud je proces spuštěn pod jiným než přihlášeným uživatelem. Vlastník procesu je uveden v **uživatelské jméno** sloupec **procesy** karty ve Správci úloh Windows. |
   | [/ crosssession](../profiling/crosssession.md) | Umožňuje profilování procesů v jiných relacích. Tato možnost je vyžadována, pokud je aplikace ASP.NET spuštěna v jiné relaci. Relace je vypsán ve **ID relace** sloupec **procesy** karty ve Správci úloh Windows. **Protokolovacímu** může být zadán jako zkratka pro **/crosssession**. |
   | [/globaloff](../profiling/globalon-and-globaloff.md) | Spuštění, které se shromažďováním dat profileru pozastaveno. Použití [globalon](../profiling/globalon-and-globaloff.md) obnovu profilování provedete. |
   | [/ Čítač](../profiling/counter.md) **:** `Config` | Shromažďuje informace z čítače výkonu procesoru, který je zadán v `Config`. Informace čítače se přidají do dat shromážděných při každé události profilování. |
   | [/wincounter](../profiling/wincounter.md) **:** `WinCounterPath` | Určuje čítač výkonu Windows má být shromážděn během profilování. |
   | [/automark](../profiling/automark.md) **:** `Interval` | Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500 ms. |
   | [/Events](../profiling/events-vsperfcmd.md) **:** `Config` | Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (. *ETL*) soubor. |

5. Spusťte cílovou aplikaci z okna příkazového řádku.

## <a name="control-data-collection"></a>Řízení shromažďování dat
 Pokud je cílová aplikace spuštěna, lze sběr dat řídit spouštěním či pozastavováním zápisu dat do datového souboru profilování pomocí *VSPerfCmd.exe* možnosti. Řízení sběru dat umožňuje shromažďovat data pro určitou část provádění programu, například spouštění či ukončování aplikace.

#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat

- Následující páry možností spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví ( **/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí ( **/processon**) nebo zastaví ( **/processoff**) sběr dat pro proces určený identifikátorem procesu (`PID`).|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí ( **/threadon**) nebo zastaví ( **/threadoff**) sběr dat pro vlákno určené pomocí ID vlákna (`TID`).|

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování
 Chcete-li ukončit relaci profilování, ukončete aplikaci, ve které běží instrumentovaná komponenta. Volání **VSPerfCmd** [/Shutdown](../profiling/shutdown.md) možnost se profiler vypne a uzavře soubor dat profilování. **VSPerfClrEnv / off** příkaz vymaže proměnné prostředí profilování.

#### <a name="to-end-a-profiling-session"></a>Chcete-li ukončit relaci profilování

1. Ukončete cílovou aplikaci.

2. Vypněte profiler. Typ:

     **/ Shutdown VSPerfCmd**

3. (Volitelné) Vyčistěte proměnné prostředí profilování. Typ:

     **Vsperfclrenv – / vypnuté**

## <a name="see-also"></a>Viz také:
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)