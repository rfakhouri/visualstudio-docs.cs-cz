---
title: Diagnostika problémů po nasazení | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a3463eab-a352-4d17-8551-adbaad526db0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 54a29e25c19d3dae18efd967a4fb26e1cd4f576a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479608"
---
# <a name="diagnose-problems-after-deployment"></a>Diagnostika problémů po nasazení
Chcete-li diagnostikovat problémy ve vaší webové aplikaci ASP.NET po nasazení s použitím technologie IntelliTrace, obsahovat informace o sestavení s vaší verzí umožníte Visual Studio automaticky vyhledá správné zdrojové soubory a soubory symbolů, které jsou nutné k ladění protokolu IntelliTrace.  

 Pokud používáte Microsoft Monitoring Agent na ovládací prvek IntelliTrace, musíte taky nastavit nastavení monitorování výkonu aplikací na webovém serveru. To zaznamenává diagnostických událostí, když vaše aplikace běží a uloží události do souboru protokolu IntelliTrace. Můžete pak podívejte se na události v Visual Studio Enterprise (ale ne Professional nebo komunity edice), přejděte na kód, kde došlo k události, podívejte se na zaznamenané hodnoty v tomto bodě v čase a dopředný nebo zpětné pohyb kód, který spustil. Po najít a opravit problém, opakujte cyklus k vytvoření, vydání a monitorovat vaši verzi, můžete vyřešit budoucí potenciální problémy, které jsou starší a rychlejší.  

 ![Kódu, sestavení, vydání, monitorování, Diagnostika, opravte](../debugger/media/ffr_cycle.png "FFR_Cycle")  

 **Budete potřebovat:**  
  
-   Visual Studio 2017, Visual Studio 2015 nebo Team Foundation Server 2017, 2015 2013, 2012 nebo 2010 tak, aby nastavení buildu  
  
-   Microsoft Monitoring Agent monitorování aplikací a záznam diagnostických dat  

-   Visual Studio Enterprise (ale ne edice Professional nebo komunity) ke kontrole diagnostických dat a ladění kódu s použitím technologie IntelliTrace  

##  <a name="SetUpBuild"></a> Krok 1: Zahrnují informace s vaší verzí sestavení  
 Nastavte vaše procesu sestavení pro vytvoření manifestu sestavení (soubor BuildInfo.config) pro webový projekt a zahrnout tento manifest s vaší verzí. Tento manifest obsahuje informace o projektu, Správa zdrojového kódu a sestavení systém, který jste použili k vytvoření konkrétní sestavení. Tyto informace pomáhají najít odpovídající zdroj a symboly po otevření protokolu IntelliTrace, který chcete ověřit zaznamenané události sady Visual Studio.  

###  <a name="AutomatedBuild"></a> Vytvoření manifestu sestavení automatizované sestavení pomocí serveru Team Foundation Server  
  
 Podle těchto kroků, zda používáte správy verzí Team Foundation nebo Git.  
 
 ####  <a name="TFS2017"></a> Team Foundation Server 2017

 Nastavte svou definici sestavení přidat umístění zdroje, sestavení a symboly k sestavení manifestu (soubor BuildInfo.config). Team Foundation Build automaticky vytvoří tento soubor a vloží ho do výstupní složky vašeho projektu.
  
1.  Pokud již máte definici buildu pomocí šablony ASP.NET Core (rozhraní .NET Framework), můžete buď [upravit vaší definice sestavení nebo vytvořte novou definici sestavení.](http://msdn.microsoft.com/Library/1c2eca2d-9a65-477e-9b23-0678ff7882ee)
  
     ![Zobrazení sestavení v sadě TFS 2017 definici](../debugger/media/ffr_tfs2017viewbuilddefinition.png "FFR_TFS2013ViewBuildDefinition")
  
2.  Pokud vytvoříte novou šablonu, zvolte šablonu ASP.NET Core (rozhraní .NET Framework). 
  
     ![Výběr šablony procesu sestavení &#45; TFS 2017](../debugger/media/ffr_tfs2017buildprocesstemplate.png "FFR_TFS2013BuildProcessTemplate")  
  
3.  Určení místa k uložení souboru symboly (PDB) tak, aby váš zdroj je indexovaný automaticky.  
  
     Pokud používáte vlastní šablonu, ujistěte se, že šablona má aktivitu pro indexování zdroje. Později přidáte argumentu MSBuild zadejte, kam chcete uložit soubory symbolů.
  
     ![Nastavit cestu symboly v definici sestavení TFS 2017](../debugger/media/ffr_tfs2017builddefsymbolspath.png "FFR_TFS2013BuildDefSymbolsPath")  
  
     Další informace o symbolech najdete v tématu [publikovat symbol data](http://msdn.microsoft.com/Library/bd6977ca-e30a-491a-a153-671d81222ce6).  
  
4.  Přidejte tento argument MSBuild mají být zahrnuty vaší sady TFS a symboly umístění souboru manifestu sestavení:  
  
     **/p:IncludeServerNameInBuildInfo = true**  
  
     Tato místa v manifestu sestavení obsah uvidí kdokoliv, kdo má přístup k webovému serveru. Ujistěte se, že váš zdrojový server je bezpečné.
  
6.  Spusťte nové sestavení.  
  
    Přejděte na [krok 2: verze aplikace](#DeployRelease)  

####  <a name="TFS2013"></a> Team Foundation Server 2013  
 Nastavte svou definici sestavení přidat umístění zdroje, sestavení a symboly k sestavení manifestu (soubor BuildInfo.config). Team Foundation Build automaticky vytvoří tento soubor a vloží ho do výstupní složky vašeho projektu.  

1.  [Upravte svou definici sestavení nebo vytvořte novou definici sestavení.](http://msdn.microsoft.com/Library/1c2eca2d-9a65-477e-9b23-0678ff7882ee)  

     ![Zobrazení sestavení v sadě TFS 2013 definici](../debugger/media/ffr_tfs2013viewbuilddefinition.png "FFR_TFS2013ViewBuildDefinition")  

2.  Zvolte výchozí šablonu (TfvcTemplate.12.xaml) nebo vlastní šablonu.  

     ![Výběr šablony procesu sestavení &#45; TFS 2013](../debugger/media/ffr_tfs2013buildprocesstemplate.png "FFR_TFS2013BuildProcessTemplate")  

3.  Určení místa k uložení souboru symboly (PDB) tak, aby váš zdroj je indexovaný automaticky.  

     Pokud používáte vlastní šablonu, ujistěte se, že šablona má aktivitu pro indexování zdroje. Později přidáte argumentu MSBuild zadejte, kam chcete uložit soubory symbolů.  

     ![Nastavit cestu symboly v definici sestavení TFS 2013](../debugger/media/ffr_tfs2013builddefsymbolspath.png "FFR_TFS2013BuildDefSymbolsPath")  

     Další informace o symbolech najdete v tématu [publikovat symbol data](http://msdn.microsoft.com/Library/bd6977ca-e30a-491a-a153-671d81222ce6).  

4.  Přidejte tento argument MSBuild mají být zahrnuty vaší sady TFS a symboly umístění souboru manifestu sestavení:  

     **/p:IncludeServerNameInBuildInfo = true**  
  
     Tato místa v manifestu sestavení obsah uvidí kdokoliv, kdo má přístup k webovému serveru. Ujistěte se, že váš zdrojový server je bezpečné.

5.  Pokud chcete použít vlastní šablonu, přidejte tento argument MSBuild k určení místa k uložení souboru symboly:  
  
     **/p:BuildSymbolStorePath =**\<*cesta k symbolům*>  
  
     ![Zahrnout informace o sestavení serveru def sestavení TFS 2013](../debugger/media/ffr_tfs2013builddefincludeserverinfo.png "FFR_TFS2013BuildDefIncludeServerInfo")  
  
     A přidejte tyto řádky do souboru webového projektu (.csproj, .vbproj):  
  
    ```  
    <!-- Import the targets file. Change the folder location as necessary. -->  
       <Import Project=""$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v$(VisualStudioVersion)\BuildInfo\Microsoft.VisualStudio.ReleaseManagement.BuildInfo.targets" />  
  
    ```  

     Tato místa v manifestu sestavení obsah uvidí kdokoliv, kdo má přístup k webovému serveru. Ujistěte se, že váš zdrojový server je bezpečné.  

6.  Spusťte nové sestavení.  

    Přejděte na [krok 2: verze aplikace](#DeployRelease)  

####  <a name="TFS2012_2010"></a> Team Foundation Server 2012 nebo 2010  
 Postupujte podle těchto kroků pro automatické vytvoření manifestu sestavení (soubor BuildInfo.config) pro svůj projekt a umístit soubor do výstupní složky vašeho projektu. Soubor se zobrazí jako "*ProjectName*. BuildInfo.config"v zadané výstupní složce, ale je přejmenován"BuildInfo.config"ve složce nasazení po publikování aplikace.  

1.  Nainstalujte Visual Studio 2013 (všechny edice) na serveru Team Foundation build.  

2.  V rámci definice sestavení zadejte umístění pro ukládání symbolů tak, aby byl zdroj automaticky indexován.  

     Pokud používáte vlastní šablonu, ujistěte se, že šablona má aktivitu pro indexování zdroje.  

3.  Do definice sestavení přidejte následující argumenty nástroje MSBuild:  

    -   **/p:VisualStudioVersion = 12.0**  

    -   **/p:MSBuildAssemblyVersion = 12.0**  

    -   **/TV:12.0**  

    -   **/p:IncludeServerNameInBuildInfo = true**  

    -   **/p:BuildSymbolStorePath =**\<*cesta k symbolům*>  

4.  Spusťte nové sestavení.  

    Přejděte na [krok 2: verze aplikace](#DeployRelease)  

###  <a name="ManualBuild"></a> Vytvoření manifestu sestavení pro ruční sestavení pomocí sady Visual Studio  
 Postupujte podle těchto kroků pro automatické vytvoření manifestu sestavení (soubor BuildInfo.config) pro svůj projekt a umístit soubor do výstupní složky vašeho projektu. Soubor se zobrazí jako "*ProjectName*. BuildInfo.config"v zadané výstupní složce, ale je přejmenován"BuildInfo.config"ve složce nasazení po publikování aplikace.  

1.  V **Průzkumníku**, uvolnit webového projektu.  

2.  Otevřete soubor projektu (.csproj, .vbproj). Přidejte tyto řádky:  

    ```xml  
    <!-- **************************************************** -->  
    <!-- Build info -->  
    <PropertyGroup>  
       <!-- Generate the BuildInfo.config file -->  
       <GenerateBuildInfoConfigFile>True</GenerateBuildInfoConfigFile>  
       <!-- Include server name in build info -->   
       <IncludeServerNameInBuildInfo>True</IncludeServerNameInBuildInfo>   
       <!-- Include the symbols path so Visual Studio can find the matching deployed code when you start debugging. -->  
       <BuildSymbolStorePath><path to symbols></BuildSymbolStorePath>  
    </PropertyGroup>  
    <!-- **************************************************** -->  
    ```  

3.  Proveďte vrácení aktualizovaného souboru projektu se změnami.  

4.  Spusťte nové sestavení.  

    Přejděte na [krok 2: verze aplikace](#DeployRelease)  

###  <a name="MSBuild"></a> Vytvoření manifestu sestavení pro ruční sestavení pomocí MSBuild.exe  
 Přidáte že tyto sestavení argumenty při spuštění sestavení:  

 **/p:GenerateBuildInfoConfigFile = true**  

 **/p:IncludeServerNameInBuildInfo = true**  

 **/p:BuildSymbolStorePath =**\<*cesta k symbolům*>  

##  <a name="DeployRelease"></a> Krok 2: Verze aplikace  
 Pokud použijete [Web.Deploy balíček](http://msdn.microsoft.com/library/dd394698.aspx) , byla vytvořena procesem sestavení k nasazení své aplikace, manifest sestavení je automaticky přejmenován ze "*ProjectName*. BuildInfo.config"na"BuildInfo.config"a je umístěn ve stejné složce pomocí souboru Web.config vaší aplikace na vašem webovém serveru.  

 Pokud používáte jiné metody k nasazení své aplikace, ujistěte se, zda manifest sestavení je přejmenován ze "*ProjectName*. BuildInfo.config"na"BuildInfo.config"a je umístěn ve stejné složce pomocí souboru Web.config vaší aplikace na webovém serveru.  

## <a name="step-3-monitor-your-app"></a>Krok 3: Sledování vaší aplikace  
 Nastavte monitorování výkonu aplikací na webovém serveru, aby mohli sledování aplikace problémů, záznamů diagnostických událostí a uložit tyto události do souboru protokolu IntelliTrace. V tématu [monitorování vaší verze pro nasazení problémy](../debugger/using-the-intellitrace-stand-alone-collector.md).  

##  <a name="InvestigateEvents"></a> Krok 4: Najít problém  
 Visual Studio Enterprise musíte na svém vývojovém počítači nebo do jiného počítače ke kontrole zaznamenané události a ladění kódu pomocí IntelliTrace. Můžete použít také nástroje, například Codelensu, mapy ladicího programu a map kódu k diagnostice problému.  

### <a name="open-the-intellitrace-log-and-matching-solution"></a>Otevření protokolu nástroje IntelliTrace a odpovídajícího řešení  

1.  Otevření protokolu IntelliTrace (soubor .iTrace) z Visual Studio Enterprise. Nebo právě poklikejte na soubor, pokud máte Visual Studio Enterprise na stejném počítači.  

2.  Zvolte **otevřete řešení** mít Visual Studio automaticky otevře odpovídající řešení nebo projektu, pokud projekt nebyl vytvořen jako součást řešení. [Otázka: v protokolu IntelliTrace chybí informace o mé nasazené aplikace. Proč tomu? Co mám udělat?](#InvalidConfigFile)  

     Visual Studio automaticky police všechny čekající změny, po jejím otevření odpovídající řešení nebo projektu. Chcete-li získat další podrobnosti o této odložených změn, podívejte se do **výstup** okno nebo **Team Explorer**.  

     Před provedením jakýchkoli změn, ujistěte se, že máte správný zdroj. Pokud chcete použít, vytvoření větve, pravděpodobně pracujete v různých větve, než kde Visual Studio najde odpovídající zdroj, jako je verze větev.  

     ![Otevřít řešení z protokolu IntelliTrace](../debugger/media/ffr_itsummarypageopensolution.png "FFR_ITSummaryPageOpenSolution")  

     Pokud máte existujícímu pracovnímu prostoru namapované na toto řešení nebo produktu project, Visual Studio vybere tento pracovní prostor pro umístění zdroje, který našel.  

     ![Otevřete od správy zdrojového kódu do pracovního prostoru namapované](../debugger/media/ffr_openprojectfromsourcecontrol_mapped.png "FFR_OpenProjectFromSourceControl_Mapped")  

     V opačném případě zvolte jiný pracovní prostor nebo vytvořte nový pracovní prostor. Sada Visual Studio bude mapovat celou větev na tento pracovní prostor.  

     ![Otevřete od správy zdrojového kódu &#45; vytvořit nový pracovní prostor](../debugger/media/ffr_openprojectfromsourcecontrol_createnewworkspace.png "FFR_OpenProjectFromSourceControl_CreateNewWorkspace")  

     Chcete-li vytvořit pracovní prostor s konkrétní mapování nebo s názvem, který není názvu vašeho počítače, zvolte **spravovat**.  

     [Otázka: Proč Visual Studio říká, že je pracovní prostor vybrané není vhodná?](#IneligibleWorkspace)  

     [Otázka: Proč nemůže pokračovat dokud zvolit kolekci týmových nebo jinou kolekci?](#ChooseTeamProject)  

### <a name="diagnose-a-performance-problem"></a>Diagnostikování problému s výkonem  

1.  V části **narušení výkonu**, zkontrolujte události zaznamenané výkonu, časy jejich celkový počet provedení a dalších informací o události. Pak přejděte hlouběji do metod, které byly volány během konkrétní události výkonu.  

     ![Zobrazit podrobnosti o událostech výkonu](../debugger/media/ffr_itsummarypageperformance.png "FFR_ITSummaryPagePerformance")  

     Můžete také pouze dvakrát kliknout na událost.  

2.  Na stránce události zkontrolujte časy spuštění těchto volání. Vyhledejte pomalé volání ve stromu spuštění.  

     Pokud máte více volání vnořených nebo jiných, zobrazují se nejpomalejší volání ve vlastním oddílu.  

     Rozbalte volání za účelem kontroly všech vnořených volání a hodnot, které byly zaznamenány v daném časovém okamžiku. Potom spusťte ladění z tohoto volání.  

     ![Spuštění ladění z volání metody](../debugger/media/ffr_itsummarypageperformancemethodscalled.png "FFR_ITSummaryPagePerformanceMethodsCalled")  

     Můžete také pouze dvakrát kliknout na volání.  

     Pokud je metoda v kódu aplikace, sada Visual Studio přejde na tuto metodu.  

     ![Přejděte do kódu aplikace z události výkonu](../debugger/media/ffr_itsummarypageperformancegotocode.png "FFR_ITSummaryPagePerformanceGoToCode")  

     Teď můžete zkontrolovat ostatní zaznamenaná hodnoty, zásobník volání krokovat kód, nebo použijte **IntelliTrace** okna [přesunout zpětné nebo dopředný "v čase" mezi jiné metody](../debugger/intellitrace.md) byly během volat Tato událost výkonu. [Co je všechny tyto další události a informace v protokolu IntelliTrace? ](../debugger/using-saved-intellitrace-data.md) [Co můžete udělat z tohoto umístění?](#WhatElse) [Chcete další informace o událostech výkonu?](http://blogs.msdn.com/b/visualstudioalm/archive/2013/09/20/performance-details-in-intellitrace.aspx)  

### <a name="diagnose-an-exception"></a>Diagnostikování výjimky  

1.  V části **Data výjimky**, zkontrolujte události zaznamenané výjimky, jejich typy, zprávy, a když se stalo výjimky. Pokud se chcete dostat hlouběji do kódu, spusťte ladění od poslední události ve skupině výjimek.  

     ![Spuštění ladění ze události výjimky](../debugger/media/ffr_itsummarypageexception.png "FFR_ITSummaryPageException")  

     Můžete také pouze dvakrát kliknout na událost.  

     Pokud došlo k výjimce v kódu aplikace, sada Visual Studio pokračuje tam, kde došlo k výjimce.  

     ![Přejděte do kódu aplikace z události výjimky](../debugger/media/ffr_itsummarypageexceptiongotocode.png "FFR_ITSummaryPageExceptionGoToCode")  

     Teď můžete zkontrolovat ostatní zaznamenaná hodnoty, zásobník volání, nebo můžete použít **IntelliTrace** okna [přesunout zpětné nebo dopředný "v čase" mezi další zaznamenané události](../debugger/intellitrace.md), související kód a zaznamenají na hodnoty Tyto body v čase. [Co je všechny tyto další události a informace v protokolu IntelliTrace?](../debugger/using-saved-intellitrace-data.md)  

###  <a name="WhatElse"></a> Co můžete dělat z tohoto umístění?  

-   [Další informace o tomto kódu](../ide/find-code-changes-and-other-history-with-codelens.md). Najít odkazy na tento kód, jeho historie změn, související chyby, pracovních položek, recenze kódu nebo testy jednotek – vše bez opuštění editoru – pomocí Codelensu indikátory v editoru.  

     ![Codelensu &#45; zobrazovat odkazy na tento kód](../debugger/media/ffr_itsummarypageperformancecodelensreferences.png "FFR_ITSummaryPagePerformanceCodeLensReferences")  

     ![Codelensu &#45; zobrazení historie pro tento kód změn](../debugger/media/ffr_itsummarypageperformancecodelensauthors.png "FFR_ITSummaryPagePerformanceCodeLensAuthors")  

-   [Při ladění, namapujte vaše místní v kódu.](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md) Chcete-li vizuálně sledovat metody, které byly volány během relace ladění, namapujte zásobník volání.  

     ![Mapování zásobníku volání při ladění](../debugger/media/ffr_itsummarypageperformancedebuggermap.png "FFR_ITSummaryPagePerformanceDebuggerMap")  

###  <a name="FAQ"></a> Q & A  

####  <a name="WhyInclude"></a> Otázka: Proč obsahují informace o projektu, Správa zdrojového kódu, sestavení a symboly Moje verze?  
 Visual Studio použije tyto informace se najít odpovídající řešení a zdroj pro tuto verzi, který se pokoušíte ladění. Po otevření protokolu IntelliTrace a vyberte událost spustit ladění, Visual Studio použije symboly najít a zobrazí kód kdy k události došlo. Potom můžete podívejte se na hodnoty, které nebyly zaznamenány a dopředný nebo zpětné pohyb spouštění vašeho kódu.  

 Pokud používáte sady TFS a tyto informace se v sestavení manifestu (soubor BuildInfo.config), vypadá Visual Studio pro odpovídající zdroj a symboly na vaše aktuálně připojené sady TFS. Pokud Visual Studio nemůže najít správný sady TFS nebo odpovídající zdroj, budete vyzváni k výběru jiné sady TFS.  

####  <a name="InvalidConfigFile"></a> Otázka: v protokolu IntelliTrace chybí informace o mé nasazené aplikace. Proč tomu? Co mám udělat?  
 To může dojít v případě nasazení z vývojovém počítači nebo nejsou připojené do sady TFS během nasazení.  

1.  Přejděte do složky pro váš projekt nasazení.  

2.  Najít a otevřít sestavení manifestu (soubor BuildInfo.config).  

3.  Ujistěte se, zda že má soubor požadované informace:  

-   **ProjectName**  

     Název projektu v sadě Visual Studio. Příklad:  

    ```  
    <ProjectName>FabrikamFiber.Extranet.Web</ProjectName>  
    ```  

-   **SourceControl**  

-   Informace o systému správy zdrojů a tyto povinných vlastností:  

    -   **SADY TFS**  

        -   **ProjectCollectionUri**: identifikátoru URI pro Team Foundation Server a project kolekce  

        -   **ProjectItemSpec**: cesta k souboru projektu vaší aplikace (.csproj nebo .vbproj)  

        -   **ProjectVersionSpec**: verze pro svůj projekt  

         Příklad:  

        ```  
        <SourceControl type="TFS">  
           <TfsSourceControl>  
              <ProjectCollectionUri>http://fabrikamfiber:8080/tfs/FabrikamFiber</ProjectCollectionUri>  
              <ProjectItemSpec>$/WorkInProgress/FabrikamFiber/FabrikamFiber.CallCenter/FabrikamFiber.Web/FabrikamFiber.Web.csproj</ProjectItemSpec>  
              <ProjectVersionSpec>LFabrikamFiber_BuildAndPublish_20130813@$/WorkInProgress</ProjectVersionSpec>  
           </TfsSourceControl>  
        </SourceControl>  
        ```  

    -   **Git**  

        -   **GitSourceControl**: umístění **GitSourceControl** schématu  

        -   **RepositoryUrl**: identifikátoru URI pro Team Foundation Server, kolekce projektů a úložiště Git  

        -   **ProjectPath**: cesta k souboru projektu vaší aplikace (.csproj nebo .vbproj)  

        -   **CommitId**: id pro vaše potvrzení  

         Příklad:  

        ```  
        <SourceControl type="Git">   
           <GitSourceControl xmlns="http://schemas.microsoft.com/visualstudio/deploymentevent_git/2013/09">  
              <RepositoryUrl>http://gittf:8080/tfs/defaultcollection/_git/FabrikamFiber</RepositoryUrl>  
              <ProjectPath>/FabrikamFiber.CallCenter/FabrikamFiber.Web/FabrikamFiber.Web.csproj</ProjectPath>  
              <CommitId>50662c96502dddaae5cd5ced962d9f14ec5bc64d</CommitId>  
           </GitSourceControl>  
        </SourceControl>  
        ```  

-   **Sestavení**  

     Informace o systém sestavení, buď `"TeamBuild"` nebo `"MSBuild"`, a následující požadované vlastnosti:  

    -   **BuildLabel** (pro TeamBuild): název sestavení a číslo. Tento popisek se také používá jako název události nasazení. Další informace o čísla sestavení najdete v tématu [použijte sestavení čísel na smysluplné názvy předáte dokončené sestavení](http://msdn.microsoft.com/Library/1f302e9d-4b0a-40b5-8009-b69ca6f988c3).  

    -   **Symbolpath –** (doporučeno): seznam identifikátorů URI pro umístění vaší symboly (soubor PDB) oddělených středníky. Tyto identifikátory URI může být adresy URL nebo adresy UNC. Díky tomu je snazší pro sadu Visual Studio se najít odpovídající symboly vám pomohou při ladění.  

    -   **BuildReportUrl** (pro TeamBuild): umístění sestavy sestavení v sadě TFS  

    -   **BuildId** (pro TeamBuild): Podrobnosti identifikátoru URI pro sestavení v sadě TFS. Tento identifikátor URI se také používá jako ID nasazení události. Toto musí id musí být jedinečný, pokud nepoužíváte TeamBuild.  

    -   **BuiltSolution**: cesta k souboru řešení používá sadou Visual Studio můžete najít a otevřít odpovídající řešení. Toto je obsah **SolutionPath** vlastnosti MsBuild.  

     Příklad:  

    -   **SADY TFS**  

        ```  
        <Build type="TeamBuild">  
           <MsBuild>  
              <BuildLabel kind="label">FabrikamFiber_BuildAndPublish_20130813.1</BuildLabel>  
              <SymbolPath>\\fabrikamfiber\FabrikamFiber.CallCenter\Symbols</SymbolPath>  
              <BuildReportUrl kind="informative, url" url="http://fabrikamfiber:8080/tfs/FabrikamFiber/_releasePipeline/FindRelease?buildUri=fabrikamfiber%3a%2f%2f%2fBuild%2fBuild%2f448">Build Report Url</BuildReportUrl>  
              <BuildId kind="id">1c4444d2-518d-4673-a590-dce2773c7744,fabrikamfiber:///Build/Build/448</BuildId>  
              <BuiltSolution>$/WorkInProgress/FabrikamFiber/FabrikamFiber.CallCenter/FabrikamFiber.CallCenter.sln</BuiltSolution>  
           </MsBuild>  
        </Build>  
        ```  

    -   **Git**  

        ```  
        <Build type="MSBuild">   
           <MSBuild>  
              <SymbolPath>\\gittf\FabrikamFiber.CallCenter\Symbols</SymbolPath>  
              <BuiltSolution>/FabrikamFiber.CallCenter/FabrikamFiber.CallCenter.sln</BuiltSolution>  
           </MSBuild>  
        </Build>  
        ```  

####  <a name="IneligibleWorkspace"></a> Otázka: Proč Visual Studio říká, že je pracovní prostor vybrané není vhodná?  
 **Odpověď:** vybraný pracovní prostor nemá žádné mapování mezi zdrojové složce řízení a do místní složky. Chcete-li vytvořit mapování pro tento pracovní prostor, zvolte **spravovat**. V opačném případě zvolte již namapovaný pracovní prostor nebo vytvořte nový pracovní prostor.  

 ![Otevřete od správy zdrojového kódu se žádné namapované prostoru](../debugger/media/ffr_openprojectfromsourcecontrol_notmapped.png "FFR_OpenProjectFromSourceControl_NotMapped")  

####  <a name="ChooseTeamProject"></a> Otázka: Proč nemůže pokračovat dokud zvolit kolekci týmových nebo jinou kolekci?  
 **Odpověď:** k tomu může dojít z některého z těchto důvodů:  

-   Sada Visual Studio není připojena k serveru TFS.  

     ![Otevřete od správy zdrojového kódu &#45; Nepřipojeno](../debugger/media/ffr_openprojectfromsourcecontrol_notconnected.png "FFR_OpenProjectFromSourceControl_NotConnected")  

-   Sada Visual Studio nenašla řešení nebo projekt v aktuální kolekci týmu.  

     Po vytvoření souboru manifestu (\<*ProjectName*>. BuildInfo.config) neuvádí, kde Visual Studio můžete najít odpovídající zdroj Visual Studio použije vaše aktuálně připojené TFS najít odpovídající řešení nebo projektu. Pokud nemá aktuální kolekce týmu odpovídající zdroj, vyzve vás sada Visual Studio k připojení k jiné kolekci týmu.  

-   Visual Studio nebyl nalezen řešení nebo produktu project v kolekci uvedené v souboru manifestu sestavení (\<*ProjectName*>. BuildInfo.config).  

     Zadaný server TFS nemusí již mít odpovídající nebo dokonce existující zdroj. Možným důvodem je, že jste migrovali na nový server TFS. Pokud zadaný server TFS neexistuje, může přibližně po minutě vypršet časový limit sady Visual Studio a poté budete vyzváni k připojení do jiné kolekce. Chcete-li pokračovat, připojte se ke správnému serveru TFS.  

     ![Otevřete od správy zdrojového kódu &#45; migrovat](../debugger/media/ffr_openprojectfromsourcecontrol_migrated.png "FFR_OpenProjectFromSourceControl_Migrated")  

####  <a name="WhatWorkspace"></a> Otázka: co je pracovního prostoru?  
 **Odpověď:** vaše [prostoru ukládá kopie zdroje](http://msdn.microsoft.com/Library/1d7f6ed8-ec7c-48f8-86da-9aea55a90d5a) vám umožní vývoj a testování samostatně před zahájením kontroly v práci. Pokud ještě nemáte pracovní prostor, který je přímo namapován na nalezené řešení nebo projekt, pak vás sada Visual Studio vyzve k výběru dostupného pracovního prostoru nebo k vytvoření nového pracovního prostoru s názvem vašeho počítače jako výchozím názvem pracovního prostoru.  

####  <a name="UntrustedSymbols"></a> Otázka: Proč se zobrazí tato zpráva o nedůvěryhodné symboly?  
 ![Ladění s cestou nedůvěryhodné symboly? ] (../debugger/media/ffr_ituntrustedsymbolpaths.png "FFR_ITUntrustedSymbolPaths")  

 **Odpověď:** tato zpráva se zobrazí, když symboly cestu v souboru manifestu sestavení (\<*ProjectName*>. BuildInfo.config) není zahrnutý v seznamu důvěryhodných symbol cest. Cestu můžete přidat do seznamu cest symbolů v možnostech ladicího programu.
