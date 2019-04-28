---
title: 'Návod: Profilace z příkazového řádku pomocí vzorkování | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1c76fd1d18b41073bf92ed18dadeeeb3a90c9209
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63433615"
---
# <a name="walkthrough-command-line-profiling-using-sampling"></a>Návod: Příkazový řádek profilování pomocí vzorkování

Tento návod ukazuje, jak chcete-li Profilovat aplikaci pomocí nástroje příkazového řádku a vzorkování identifikovat problémy s výkonem.

V tomto názorném postupu projít procesem profilaci spravované aplikace pomocí nástrojů příkazového řádku a pomocí vzorkování izolovat a identifikovat problémy s výkonem v aplikaci.

V tomto podrobném návodu postupujte podle těchto kroků:

- Profilovat aplikaci pomocí nástrojů příkazového řádku a vzorkování.
- Analýza vzorky profilování výsledků k vyhledání a opravě problémů s výkonem.

## <a name="prerequisites"></a>Požadavky

- Zprostředkující znalost [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)]
- Zprostředkující znalost práce pomocí nástrojů příkazového řádku
- Kopie [peopletrax – ukázka](/visualstudio/profiling/performance-explorer)
- Pro práci s profilace na základě informací poskytnutých, je nejlepší mít ladění k dispozici informace o symbolech.

## <a name="command-line-profiling-using-the-sampling-method"></a>Profilace z příkazového řádku pomocí metody vzorkování

Vzorkování je metodě profilování pomocí kterého konkrétní proces pravidelně dotazovaní určit aktivní funkce. Výsledná data poskytuje přehled o četnosti funkce byla vrcholu zásobníku volání při procesu vzorkováno.

> [!NOTE]
> Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.

### <a name="to-profile-the-peopletrax-application-by-using-the-sampling-method"></a>Chcete-li Profilovat aplikaci PeopleTrax pomocí metody vzorkování

1. Nainstalovat ukázkovou aplikaci peopletrax – a vytvářet verze aplikace.

2. Otevřete okno příkazového řádku a přidejte adresář nástrojů profilování do místní proměnné prostředí Path.

3. Změňte pracovní adresář na adresář, který obsahují PeopleTrax binární soubory.

4. Zadejte následující příkaz nastavit příslušné proměnné prostředí:

    ```cmd
    VSPerfCLREnv /sampleon
    ```

5. Spustit profilování spuštěním *VSPerfCmd.exe*, což je nástroj příkazového řádku, který řídí profileru. Následující příkaz spustí v režimu vzorkování aplikace a profiler:

    ```cmd
    VsPerfCmd /start:sample /output:PeopleTraxReport.vsp /launch:PeopleTrax.exe
    ```

     Spustí se připojí k profileru proces *PeopleTrax.exe* procesu. Spustí se proces profiler zapisovat shromážděná data profilování do souboru sestavy.

6. Klikněte na tlačítko **získá osoby**.

7. Klikněte na tlačítko **ExportData**.

     Poznámkový blok se otevře a zobrazí nový soubor, který obsahuje data exportovaná z **PeopleTrax**.

8. Zavřete poznámkový blok a pak **PeopleTrax** aplikace.

9. Vypněte profiler. Zadejte následující příkaz:

    ```cmd
    VSPerfCmd /shutdown
    ```

10. Chcete-li obnovit proměnné prostředí, použijte následující příkaz:

    ```cmd
    VSPerfCLREnv /sampleoff
    ```

11. Data profilování jsou uložena v. *vsp* soubor analyzovat výsledky pomocí jedné z následujících metod:

    - Otevřít. *vsp* soubor v integrovaném vývojovém prostředí sady Visual Studio.

         – nebo –

    - Generování hodnot oddělených čárkami (. *sdílený svazek clusteru*) souborů pomocí nástroje příkazového řádku *VSPerfReport.exe*. Ke generování sestav pro použití mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí pomocí následujícího příkazu:

        ```cmd
        VSPerfReport <dir> PeopleTraxReport.vsp /output:<dir> /summary:all
        ```

## <a name="see-also"></a>Viz také:

[Přehled výkonnostní relace](../profiling/performance-session-overview.md)
[profilu z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)
[VSPerfCmd](../profiling/vsperfcmd.md)
[pochopení dat vzorkování hodnoty](../profiling/understanding-sampling-data-values.md)
[zobrazení sestav výkonu](../profiling/performance-report-views.md)