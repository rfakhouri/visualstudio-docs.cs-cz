---
title: Připojení profileru ke službě .NET ke shromažďování statistik aplikace
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a0046c47-26c8-4bec-96a0-81da05e5104a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 32aa82654d55496c3d407f59712a8b7adba56b9a
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66261547"
---
# <a name="how-to-attach-the-profiler-to-a-net-service-to-collect-application-statistics-by-using-the-command-line"></a>Postupy: Připojení profileru ke službě .NET ke shromažďování statistik aplikace pomocí příkazového řádku
Tento článek popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] služby nástroje příkazového řádku nástroje pro profilaci k připojení profileru k rozhraní .NET Framework a shromáždit statistiky výkonu pomocí metody vzorkování.

> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).
>
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.
>
> Přidání dat interakce vrstvy do běhu profilování vyžaduje zvláštní procedury s nástroji pro profilaci příkazového řádku. Zobrazit [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).

 Chcete-li shromáždit údaje o výkonu ze služby rozhraní .NET Framework, je nutné použít [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) nástroj k inicializaci příslušných proměnných prostředí. Poté je nutné restartovat počítač, který je hostitelem služby, a nakonfigurovat tento počítač pro profilování. Poté profiler připojte k procesu služby. Pokud je profiler připojen ke službě, můžete pozastavit a obnovit shromažďování dat.

 Chcete-li ukončit relaci profilování, musí být profiler odpojen od služby a poté explicitně ukončen. Ve většině případů doporučujeme na konci relace vyčistit proměnné prostředí profilování.

## <a name="attach-the-profiler"></a>Připojení profileru

#### <a name="to-attach-the-profiler-to-a-net-framework-service"></a>Připojení profileru ke službě rozhraní .NET Framework

1. Nainstalujte službu.

2. Otevřete okno příkazového řádku.

3. Inicializujte proměnné prostředí profilování. Typ:

    **Vsperfclrenv – /globalsampleon** [**/samplelineoff**]

   - **/globalsampleon** umožňuje vzorkování.

   - **/samplelineoff** zakáže přiřazení shromážděných dat ke konkrétnímu zdroji řádků kódu. Pokud je tato možnost zadána, data přiřazena pouze funkcí.

4. Restartujte počítač.

5. Otevřete okno příkazového řádku.

6. Spusťte profiler. Typ:

    **Nástroj VSPerfCmd**[/start](../profiling/start.md) **: Ukázka**[/output](../profiling/output.md) **:** `OutputFile` [`Options`]    

   - **/Start:sample** možnost inicializuje profiler.

   - **/Output:** `OutputFile` možnost je vyžadována s **/start**. `OutputFile` Určuje název a umístění souboru dat profilování (.vsp).

     Můžete použít některý z těchto možností s **/start:sample** možnost.

   > [!NOTE]
   > **/User** a **/crosssession** možnosti jsou obvykle vyžadovány pro služby.

   | Možnost | Popis |
   | - | - |
   | [/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName` | Určuje doménu a uživatelské jméno účtu vlastnícího profilovaný proces. Tato možnost je vyžadována, pouze pokud je proces spuštěn pod jiným než přihlášeným uživatelem. Vlastník procesu je uvedena ve sloupci uživatelské jméno na záložce procesy ve Správci úloh Windows. |
   | [/ crosssession](../profiling/crosssession.md) | Umožňuje profilování procesů v jiných relacích. Tato možnost je vyžadována, pokud služba běží v jiné relaci. Id relace je uvedeno ve sloupci ID relace na záložce procesy ve Správci úloh Windows. **Protokolovacímu** může být zadán jako zkratka pro **/crosssession**. |
   | [/wincounter](../profiling/wincounter.md) **:** `WinCounterPath` | Určuje čítač výkonu Windows má být shromážděn během profilování. |
   | [/automark](../profiling/automark.md) **:** `Interval` | Použití s **/wincounter** pouze. Určuje počet milisekund mezi událostmi sběru čítače výkonu Windows. Výchozí hodnota je 500 ms. |
   | [/Events](../profiling/events-vsperfcmd.md) **:** `Config` | Určuje událost trasování událostí pro Windows (ETW) má být shromážděn během profilování. Události trasování událostí pro Windows jsou shromážděny v samostatném (ETL) soubor. |

7. V případě potřeby spusťte službu.

8. Připojení profileru ke službě. Typ:

    **Nástroj VSPerfCmd**[/ attach](../profiling/attach.md) **:** {`PID`&#124;`ProcName`} [`Sample Event`] [[targetclr](../profiling/targetclr.md)**:**`Version`]  

   - Zadejte identifikátor ID procesu (`PID`) nebo název procesu (ProcName) služby. ID procesů a názvy všech spuštěných procesů lze zobrazit ve Správci úloh Windows.

     Ve výchozím nastavení, data výkonu vzorkována každých procesoru 10 000 000 nepřerušených hodinových cyklů. V případě procesoru s frekvencí 1 GHz jde o přibližně 100 vzorků za sekundu. Můžete zadat jednu z následujících možností, chcete-li změnit intervalu hodinových cyklů nebo změnu událostí vyvolávajících.

   |Událost vzorku|Popis|
   |------------------|-----------------|
   |[/Timer](../profiling/timer.md) **:** `Interval`|Změní interval vzorkování na počet nepřerušených hodinových cyklů určených parametrem `Interval`.|
   |[/PF](../profiling/pf.md)[**:**`Interval`]|Změní událost odběru vzorků na chyby stránek. Pokud `Interval` je určen, nastaví počet chyb stránek mezi vzorky. Výchozí hodnota je 10.|
   |[/ sys](../profiling/sys-vsperfcmd.md)[`:``Interval`]|Změní událost odběru vzorků na volání systému z procesu do jádra operačního systému (syscalls). Pokud `Interval` je určen, nastaví počet volání mezi vzorky. Výchozí hodnota je 10.|
   |[/ Čítač](../profiling/counter.md) **:** `Config`|Změní událost a interval vzorkování na čítač výkonu a interval procesoru určený parametrem `Config`.|

   - **targetclr:** `Version` Určuje verzi modulu common language runtime (CLR) do profilu je do aplikace načtena více než jedna verze modulu runtime. Volitelné.

## <a name="control-data-collection"></a>Řízení shromažďování dat
 Pokud je služba spuštěna, můžete použít *VSPerfCmd.exe* možnosti spuštění a zastavení zápisu dat do datového souboru profilování. Řízení sběru dat umožňuje shromažďovat data pro určitou část provádění programu, například spouštění či ukončování aplikace.

#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat

- Následující páry **VSPerfCmd** možností spouští a zastavují sběr dat. Každou možnost zadejte na samostatný příkazový řádek. Sběr dat lze zapnout a vypnout několikrát.

    |Možnost|Popis|
    |------------|-----------------|
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**globalon**) nebo zastaví (**/globaloff**) sběr dat pro všechny procesy.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) sběr dat pro proces určený identifikátorem procesu (`PID`).|
    |**/ attach:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ attach** spustí sběr dat pro proces určený pomocí ID procesu nebo názvem procesu. **/ detach** zastaví sběr dat pro zadaný proces nebo pro všechny procesy, pokud konkrétní proces není zadán.|

## <a name="end-the-profiling-session"></a>Ukončit relaci profilování
 Chcete-li ukončit relaci profilování, musí být profiler odpojen od všech profilovaných procesů a profiler musí být explicitně vypnut. Můžete odpojit od aplikace profilované používáním metody vzorkování ukončením aplikace nebo zavoláním **VSPerfCmd / detach** možnost. Poté je zapotřebí zavolat **VSPerfCmd/Shutdown** možnost profiler vypne a uzavře soubor dat profilování.

 **VSPerfClrEnv /globaloff** příkaz vymaže proměnné prostředí profilování, ale konfigurace systému není obnovena, až po restartování počítače.

#### <a name="to-end-a-profiling-session"></a>Chcete-li ukončit relaci profilování

1. Proveďte jednu z následujících-li odpojit profiler od cílové aplikace:

    - Zastavte službu.

         -nebo-

    - Typ **VSPerfCmd / odpojení**

2. Vypněte profiler. Typ:

     **/ Shutdown VSPerfCmd**

3. (Volitelné) Vyčistěte proměnné prostředí profilování. Typ:

     **Vsperfclrenv – /globaloff**

4. Restartujte počítač.

## <a name="see-also"></a>Viz také:
- [Profil služby](../profiling/command-line-profiling-of-services.md)
- [Zobrazení dat metod vzorkování](../profiling/profiler-sampling-method-data-views.md)