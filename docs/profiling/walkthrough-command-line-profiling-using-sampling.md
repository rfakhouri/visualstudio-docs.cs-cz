---
title: 'Návod: Profilace z příkazového řádku pomocí vzorkování | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 941597abd21d62501546860cf9cc8adc8fc6de2d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-command-line-profiling-using-sampling"></a>Návod: Profilace z příkazového řádku s použitím vzorkování

Tento návod ukazuje, jak do profilu aplikace pomocí nástroje příkazového řádku a vzorkování identifikovat problémy s výkonem.

V tomto návodu krok procesem profilace spravované aplikace pomocí nástroje příkazového řádku a pomocí vzorkování izolovat a identifikovat problémy s výkonem v aplikaci.

V tomto návodu se postupujte takto:

- Profil aplikace pomocí nástroje příkazového řádku a vzorkování.
- Analýza jen Vzorkovaná profilování výsledků najděte a opravte problémy s výkonem.

## <a name="prerequisites"></a>Požadavky

- Zprostředkující pochopení [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)]
- Mezilehlé pochopit práci s nástroji příkazového řádku
- Kopii [peopletrax – ukázka](../profiling/peopletrax-sample-profiling-tools.md)
- Při práci s informacemi poskytované profilace, je nejlepší mít ladění symbol informace, které jsou k dispozici.

## <a name="command-line-profiling-using-the-sampling-method"></a>Příkazový řádek profilace pomocí metody vzorkování

Vzorkování je profilování metoda, podle kterého je konkrétní proces pravidelně dotazování k určení active funkce. Výsledná data poskytuje počet jak často byl funkce v zásobníku volání při procesu byla vzorků.

> [!NOTE]
> Nástroje příkazového řádku balíku nástrojů pro profilaci jsou umístěny v podadresáři \Team Tools\Performance Tools instalačního adresáře sady Visual Studio. V 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musíte přidat cestu do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Peopletrax – je 32bitová aplikace.

### <a name="to-profile-the-peopletrax-application-by-using-the-sampling-method"></a>Do profilu aplikace PeopleTrax pomocí metody vzorkování

1. Nainstalujte aplikaci peopletrax – ukázka a sestavení verzi aplikace.

2. Otevřete okno příkazového řádku a přidejte adresář nástrojích pro profilaci do místní proměnné prostředí Path.

3. Přejděte do adresáře, které obsahují binární soubory peopletrax – pracovní adresář.

4. Zadejte následující příkaz pro nastavení příslušné proměnné prostředí:

    ```
    VSPerfCLREnv /sampleon
    ```

5. Spusťte profilování spuštěním VSPerfCmd.exe, což je nástroj příkazového řádku, které řídí profileru. Následující příkaz spustí v režimu vzorkování aplikace a profileru:

    ```
    VsPerfCmd /start:sample /output:PeopleTraxReport.vsp /launch:PeopleTrax.exe
    ```

     Proces profileru spustí a připojí k procesu PeopleTrax.exe. Spustí se proces profileru k zápisu do souboru sestavy shromážděná data profilování.

6. Klikněte na tlačítko **získat osoby**.

7. Klikněte na tlačítko **ExportData**.

     Otevře Poznámkový blok a zobrazí nový soubor, který obsahuje data exportovaná z **PeopleTrax**.

8. Zavřete poznámkový blok a pak zavřete **PeopleTrax** aplikace.

9. Vypněte profileru. Zadejte následující příkaz:

    ```
    VSPerfCmd /shutdown
    ```

10. Chcete-li obnovit proměnné prostředí použijte následující příkaz:

    ```
    VSPerfCLREnv /sampleoff
    ```

11. Profilace dat je uložený v souboru the.vsp Analyzujte výsledky pomocí jedné z následujících metod:

    - Otevřete soubor the.vsp v prostředí Visual Studio IDE.

         – nebo –

    - Pomocí nástroje příkazového řádku VSPerfReport.exe vygenerujte soubor hodnot oddělených čárkami (.csv). Ke generování sestav pro použití mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE použijte následující příkaz:

        ```
        VSPerfReport <dir> PeopleTraxReport.vsp /output:<dir> /summary:all
        ```

## <a name="see-also"></a>Viz také

[Přehled výkonnostní relace](../profiling/performance-session-overview.md)  
[Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)  
[VSPerfCmd](../profiling/vsperfcmd.md)  
[Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)  
[Zobrazení sestav výkonu](../profiling/performance-report-views.md)