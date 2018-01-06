---
title: "Návod: Profilace z příkazového řádku pomocí instrumentace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
ms.assetid: 1c6f1586-3d6a-431f-bedf-c54088e280ba
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 29a68dc22a348c787d192bebecea91caed7aa0cc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-command-line-profiling-using-instrumentation"></a>Návod: Profilace z příkazového řádku s použitím instrumentace
Tento návod provede profilace [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] samostatné aplikaci a shromažďování podrobných časování volání počet data pomocí metody instrumentace z nástroje pro profilaci. V tomto návodu se provádění následujících úloh:  
  
-   Použití [vsinstr –](../profiling/vsinstr.md) nástroj pro příkazový řádek ke generování instrumentované binární soubory.  
  
-   Použití [vsperfclrenv –](../profiling/vsperfclrenv.md) nástroj pro nastavení proměnných prostředí ke shromažďování dat profilace rozhraní .NET.  
  
-   Použití [VSPerfCmd](../profiling/vsperfcmd.md) nástroje ke shromažďování dat profilování.  
  
-   Použití [vsperfreport –](../profiling/vsperfreport.md) nástroj pro generování sestav na základě souborů profilování data.  
  
## <a name="prerequisites"></a>Požadavky  
  
-   [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)]  
  
-   Zprostředkující znalosti jazyka C#  
  
-   Mezilehlé pochopit práci s nástroji příkazového řádku  
  
-   Kopii [peopletrax – ukázka](../profiling/peopletrax-sample-profiling-tools.md)  
  
-   Při práci s informacemi poskytované profilace, je nejlepší mít ladění symbol informace, které jsou k dispozici. Další informace najdete v tématu [postupy: odkaz na informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md).  
  
## <a name="command-line-profiling-using-the-instrumentation-method"></a>Příkazový řádek profilace pomocí metody instrumentace  
 Instrumentace je profilování metoda, podle kterého speciálně integrovaný verzích PROFILOVANÉHO binární soubory obsahují testu funkce, které shromažďovat informace o časování na vstupu a výstupu k funkcím v instrumentovaného modulu. Vzhledem k tomu, že tato metoda profilace je než vzorkování, způsobuje větší objem režie. Instrumentované binární soubory jsou také větší než ladění nebo verzi binárních souborů a není určena pro nasazení.  
  
> [!NOTE]
>  Neodesílat instrumentované binární soubory pro vaše zákazníky. Instrumentované binární soubory může obsahovat několik rizika. Binární soubory zahrnují informace, které usnadňuje aplikace zpětné analýzy a také bezpečnostní rizika.  
  
#### <a name="to-profile-the-peopletrax-application-by-using-the-instrumentation-method"></a>Do profilu aplikace PeopleTrax pomocí metody instrumentace  
  
1.  Nainstalujte aplikaci peopletrax – ukázka a sestavení prodejní verze.  
  
2.  Otevřete okno příkazového řádku a přidejte **nástrojích pro profilaci** adresář do místní proměnné prostředí Path.  
  
3.  Přejděte do adresáře, který obsahuje binární soubory peopletrax – pracovní adresář.  
  
4.  Vytvořte adresář, který bude obsahovat zprávy nástroje založená na souborech. Zadejte následující příkaz:  
  
    ```  
    md Reports  
    ```  
  
5.  Vsinstr – nástroj příkazového řádku použijte k instrumentaci binárních souborů v aplikaci. Na samostatné řádky příkaz zadejte následující příkazy:  
  
    ```  
    VSInstr PeopleTrax.exe  
    VSInstr PeopleTrax.exe  
    VSInstr People.dll  
    VSInstr Person.dll  
    VSInstr Operation.dll  
    ```  
  
     **Poznámka:** ve výchozím nastavení, uloží vsinstr – zálohy instrumentovány původního souboru. Název záložního souboru má příponu. orig. Například původní verzi "MyApp.exe" by byla uložena jako "MyApp.exe.orig."  
  
6.  Zadejte následující příkaz pro nastavení příslušné proměnné prostředí:  
  
    ```  
    VsPerfCLREnv /traceon  
    ```  
  
7.  Pokud chcete spustit profileru, zadejte následující příkaz:  
  
    ```  
    VsPerfCmd /start:trace /output:Reports\Report.vsp  
    ```  
  
8.  Po spuštění profileru v režimu trasování, spusťte instrumentovaného verzi PeopleTrax.exe proces shromažďování dat.  
  
     **PeopleTrax** se zobrazí v okně aplikace.  
  
9. Klikněte na tlačítko **získat osoby**.  
  
     Datová mřížka PeopleTrax naplní s daty.  
  
10. Klikněte na tlačítko **exportovat Data**.  
  
     Spustí Poznámkový blok a zobrazí nový soubor, který obsahuje seznam osoby z **PeopleTrax** aplikace.  
  
11. Zavřete poznámkový blok a pak zavřete **PeopleTrax** aplikace.  
  
12. Vypněte profileru. Zadejte následující příkaz:  
  
    ```  
    VSPerfCmd /shutdown  
    ```  
  
13. Zadejte následující příkaz k resetování proměnné prostředí:  
  
    ```  
    VSPerfCLREnv /off  
    ```  
  
14. Použijte vsperfreport – nástroj pro generování nebo souborů sestav hodnot oddělených čárkami (.csv). Typ:  
  
    ```  
    VSPerfReport Reports\Report.vsp /output:Reports /summary:all  
    ```  
  
     Můžete analyzovat generované sestavy v tabulkového procesoru, nebo můžete použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE analyzovat data v souboru Report.vsp profilování. Další informace najdete v tématu [analýza dat nástrojů pro výkon](../profiling/analyzing-performance-tools-data.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled výkonnostní relace](../profiling/performance-session-overview.md)   
 [Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)   
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)