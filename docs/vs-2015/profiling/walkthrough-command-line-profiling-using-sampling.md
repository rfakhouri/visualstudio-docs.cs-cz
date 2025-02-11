---
title: 'Návod: Profilace z příkazového řádku pomocí vzorkování | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
ms.assetid: 1d53972f-6f35-4842-8c74-1b627f18c70a
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 96dfe49ce4e174680202cd60c3e8bca83cfbf575
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439687"
---
# <a name="walkthrough-command-line-profiling-using-sampling"></a>Návod: Příkazový řádek profilování pomocí vzorkování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento návod ukazuje, jak chcete-li Profilovat aplikaci pomocí nástroje příkazového řádku a vzorkování identifikovat problémy s výkonem.  
  
 V tomto názorném postupu projít procesem profilaci spravované aplikace pomocí nástrojů příkazového řádku a pomocí vzorkování izolovat a identifikovat problémy s výkonem v aplikaci.  
  
 V tomto podrobném návodu postupujte podle těchto kroků:  
  
- Profilovat aplikaci pomocí nástrojů příkazového řádku a vzorkování.  
  
- Analýza vzorky profilování výsledků k vyhledání a opravě problémů s výkonem.  
  
## <a name="prerequisites"></a>Požadavky  
  
- [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], nebo [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
- Zprostředkující znalost [!INCLUDE[csharp_current_short](../includes/csharp-current-short-md.md)]  
  
- Zprostředkující znalost práce pomocí nástrojů příkazového řádku  
  
- Kopie [peopletrax – ukázka](../profiling/peopletrax-sample-profiling-tools.md)  
  
- Pro práci s profilace na základě informací poskytnutých, je nejlepší mít ladění k dispozici informace o symbolech.  
  
## <a name="command-line-profiling-using-the-sampling-method"></a>Příkazového řádku pro profilaci pomocí metody vzorkování  
 Vzorkování je metodě profilování pomocí kterého konkrétní proces pravidelně dotazovaní určit aktivní funkce. Výsledná data poskytuje přehled o četnosti funkce byla vrcholu zásobníku volání při procesu vzorkováno.  
  
> [!NOTE]
> Nástroje příkazového řádku balíku nástrojů pro profilaci jsou umístěny v podadresáři \Team Tools\Performance Tools instalačního adresáře sady Visual Studio. Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Chcete-li využívat nástroje příkazového řádku profileru, musí přidat cestu do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého. Další informace najdete v tématu [zadání cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Peopletrax – je 32bitové aplikace.  
  
#### <a name="to-profile-the-peopletrax-application-by-using-the-sampling-method"></a>Chcete-li Profilovat aplikaci PeopleTrax pomocí metody vzorkování  
  
1. Nainstalovat ukázkovou aplikaci peopletrax – a vytvářet verze aplikace.  
  
2. Otevřete okno příkazového řádku a přidejte adresář nástrojů profilování do místní proměnné prostředí Path.  
  
3. Změňte pracovní adresář na adresář, který obsahují PeopleTrax binární soubory.  
  
4. Zadejte následující příkaz nastavit příslušné proměnné prostředí:  
  
    ```  
    VSPerfCLREnv /sampleon  
    ```  
  
5. Spusťte profilování spuštěním VSPerfCmd.exe, což je nástroj příkazového řádku, který řídí profileru. Následující příkaz spustí v režimu vzorkování aplikace a profiler:  
  
    ```  
    VsPerfCmd /start:sample /output:PeopleTraxReport.vsp /launch:PeopleTrax.exe  
    ```  
  
     Profiler proces spustí a připojí se k procesu PeopleTrax.exe. Spustí se proces profiler zapisovat shromážděná data profilování do souboru sestavy.  
  
6. Klikněte na tlačítko **získá osoby**.  
  
7. Klikněte na tlačítko **ExportData**.  
  
     Poznámkový blok se otevře a zobrazí nový soubor, který obsahuje data exportovaná z **PeopleTrax**.  
  
8. Zavřete poznámkový blok a pak **PeopleTrax** aplikace.  
  
9. Vypněte profiler. Zadejte následující příkaz:  
  
    ```  
    VSPerfCmd /shutdown  
    ```  
  
10. Chcete-li obnovit proměnné prostředí, použijte následující příkaz:  
  
    ```  
    VSPerfCLREnv /sampleoff  
    ```  
  
11. Data profilování jsou uloženy v souboru the.vsp analyzovat výsledky pomocí jedné z následujících metod:  
  
    - Otevřete soubor the.vsp v integrovaném vývojovém prostředí sady Visual Studio.  
  
         – nebo –  
  
    - Vygenerujte soubor hodnot oddělených čárkami (CSV) s použitím nástroje příkazového řádku VSPerfReport.exe. Ke generování sestav pro použití mimo [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrovaného vývojového prostředí pomocí následujícího příkazu:  
  
        ```  
        VSPerfReport <dir> PeopleTraxReport.vsp /output:<dir> /summary:all  
        ```  
  
## <a name="see-also"></a>Viz také  
 [Přehled výkonnostní relace](../profiling/performance-session-overview.md)   
 [Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)   
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)
