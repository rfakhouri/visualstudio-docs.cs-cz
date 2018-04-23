---
title: Pomocí uložit dat technologie IntelliTrace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.historicaldebug.norepro
helpviewer_keywords:
- iTrace files
- IntelliTrace, log files
- IntelliTrace log files
- .iTrace files
ms.assetid: 9f2cce86-345a-4e22-84ba-91542d81e67a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 54412cff3047f12ec17c8192dc40cd4ebfcbf55b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="using-saved-intellitrace-data"></a>Pomocí uložených dat technologie IntelliTrace
Při spuštění ladění ze souboru protokolu (.iTrace) IntelliTrace, přejděte na určité místo spuštění vaší aplikace. Tento soubor může obsahovat události výkonu, výjimky, vláken, testovací kroky, moduly a jiné informace systému, aby záznamy IntelliTrace při vaše aplikace běží.  
  
 Ujistěte se, zda máte následující:  
  
-   Odpovídající zdrojové soubory a soubory symbolu (.pdb) pro kód aplikace. Jinak Visual Studio nelze přeložit umístění zdrojových souborů a zobrazí zpráva "Symboly nebyl nalezen." V tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) a [Diagnostika problémů po nasazení](../debugger/diagnose-problems-after-deployment.md).  
  
-   Visual Studio Enterprise (ale ne Professional nebo komunity edice) na vývojovém počítači nebo do jiného počítače Otevřít soubory .iTrace  
  
-   Soubor .iTrace z jednoho z těchto zdrojů:  
  
    |**Zdroj**|**V tématu**|  
    |----------------|-------------|  
    |Relaci IntelliTrace ve Visual Studio Enterprise (ale ne Professional nebo komunity edice)|[Funkce IntelliTrace](../debugger/intellitrace-features.md)|  
    |Relace testování v Microsoft Test Manager. Tento soubor .iTrace připojí k pracovní položce Team Foundation Server.|[Shromažďování více diagnostických dat v manuálních testech](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|  
    |Microsoft Monitoring Agent, buď samostatně nebo pomocí System Center 2012 R2 Operations Manager pro technologii ASP.NET webové aplikace a služby SharePoint aplikace běžící v nasazení|-   [Diagnostika problémů po nasazení](../debugger/diagnose-problems-after-deployment.md)<br />-   [Co je nového pro System Center 2012 R2 Operations Manager](http://technet.microsoft.com/library/dn249700.aspx)|  
  
##  <a name="GetStarted"></a> Co chcete udělat?  
  
-   [Otevřete protokol nástroje IntelliTrace](#Open)  
  
-   [Pochopení protokolu IntelliTrace](#Understand)  
  
-   [Spuštění ladění z protokolu IntelliTrace](#StartDebugging)  
  
##  <a name="Open"></a> Otevřete protokol nástroje IntelliTrace  
 Na počítači s Visual Studio Enterprise otevřete soubor .iTrace.  
  
-   Poklikejte na soubor .iTrace mimo Visual Studio, nebo otevřít soubor z v sadě Visual Studio.  
  
     \- nebo –  
  
-   Pokud soubor .iTrace je připojen k pracovní položce Team Foundation Server, postupujte podle těchto kroků v rámci pracovní položky:  
  
    -   V části **všechny odkazy**, najít soubor .iTrace. Otevřete ji.  
  
         \- nebo –  
  
    -   V části **zkopírujte kroky**, vyberte **IntelliTrace** odkaz.  
  
> [!TIP]
>  Pokud jste zavřeli souboru nástroje IntelliTrace během ladění, můžete ho znovu otevřít snadno. Přejděte na **ladění** nabídce zvolte **IntelliTrace**, **zobrazit souhrn protokolu**. Můžete také **zobrazit souhrn protokolu** v **IntelliTrace** okno. Toto je k dispozici pouze při ladění pomocí technologie IntelliTrace.  
  
##  <a name="Understand"></a> Pochopení protokolu IntelliTrace  
 Některé z těchto částí v souboru .iTrace zobrazí pouze v případě, že jste shromáždili data z určitého zdroje, například z nástroje Test Manager nebo z aplikací služby SharePoint.  
  
|**Část**|**Obsahuje**|**Zdroj kolekce**|  
|-----------------|------------------|---------------------------|  
|[Narušení výkonu](#Performance)|Události výkonu pomocí volání funkce, které překročí nakonfigurovanou prahovou hodnotu|Microsoft Monitoring Agent, buď samostatného sběrače nebo pomocí System Center 2012 R2 Operations Manager pro webové aplikace ASP.NET hostované ve službě IIS|  
|[Data výjimky](#ExceptionData)|Výjimky, včetně zásobníku volání úplné pro jednotlivé výjimky|Všechny zdroje|  
|[Analýza](#Analysis)|SharePoint 2010 a SharePoint 2013 pouze pro aplikace. Diagnostika IntelliTrace a SharePoint událostmi, například ladicí program události, ULS události, neošetřených výjimek a další data, která zaznamenává Microsoft Monitoring Agent.|Microsoft Monitoring Agent, buď samostatného sběrače nebo pomocí System Center 2012 R2 Operations Manager|  
|[Informace o systému](#SystemInfo)|Nastavení a specifikace hostitelského systému|Všechny zdroje|  
|[Seznam vláken](#ThreadsList)|Vláken, které byly spuštěny při kolekce|Všechny zdroje|  
|[Testovacích dat](#TestData)|Kroky testů a jejich výsledky z relace testu|Test Manager|  
|[Moduly](#Modules)|Moduly, které tento cílový proces načtené v pořadí, ve kterém budou načteny.|Všechny zdroje| 
|[Webové žádosti](#Modules)|Data webové žádosti pro produkční IIS webové aplikace a služby SharePoint 2010 a SharePoint 2013|Microsoft Monitoring Agent a samostatného sběrače| 
  
 Tady je několik užitečných tipů k vám pomůžou najít informace v každé části:  
  
-   Vyberte záhlaví sloupce seřadíte data.  
  
-   Pomocí vyhledávacího pole k datům filtru. Prostý text vyhledávání funguje mezi všechny sloupce kromě sloupců čas. Můžete také filtrovat hledání na konkrétní sloupec s jeden filtr na sloupec. Zadejte název sloupce bez mezer, dvojtečka (**:**) a hledanou hodnotu. Potom zadejte středník (**;**) můžete přidat jinou hodnotu sloupce a vyhledávání.  
  
     Například k vyhledání události výkonu, které mají slovo "pomalé" v **popis** zadejte:  
  
     `Description:slow`  
  
##  <a name="StartDebugging"></a> Spuštění ladění z protokolu IntelliTrace  
  
###  <a name="Performance"></a> Narušení výkonu  
 Zkontrolujte události výkonu, které byly zaznamenány pro vaši aplikaci. Můžete skrýt, události, které nejsou často dojít.  
  
##### <a name="to-start-debugging-from-a-performance-event"></a>Spustit ladění z události výkonu.  
  
1.  V části **narušení výkonu**, zkontrolujte události zaznamenané výkonu, časy jejich celkový počet provedení a dalších informací o události. Pak přejděte hlouběji do metod, které byly volány během konkrétní události výkonu.  
  
     ![Zobrazit podrobnosti o událostech výkonu](../debugger/media/ffr_itsummarypageperformance.png "FFR_ITSummaryPagePerformance")  
  
     Můžete také pouze dvakrát kliknout na událost.  
  
2.  Na stránce události zkontrolujte časy spuštění těchto volání. Vyhledejte pomalé volání ve stromu spuštění.  
  
     Pokud máte více volání vnořených nebo jiných, zobrazují se nejpomalejší volání ve vlastním oddílu.  
  
3.  Rozbalte možnost, že volání zobrazíte všechny vnořené volání a hodnoty parametrů, které nebyly zaznamenány v tomto bodě v čase.  
  
     (Klávesové: Chcete-li zobrazit nebo skrýt vnořená volání, stiskněte **šipka vpravo** nebo **šipka doleva** klíče v uvedeném pořadí. Zobrazení a skrytí hodnoty parametrů pro volání vnořených, stiskněte **místo** klíč.)  
  
     Spusťte ladění z volání.  
  
     ![Spuštění ladění z volání metody](../debugger/media/ffr_itsummarypageperformancemethodscalled.png "FFR_ITSummaryPagePerformanceMethodsCalled")  
  
     Můžete také právě dvakrát klikněte na volání nebo stiskněte klávesu **Enter** klíč.  
  
     Pokud je metoda v kódu aplikace, sada Visual Studio přejde na tuto metodu.  
  
     ![Přejděte do kódu aplikace z události výkonu](../debugger/media/ffr_itsummarypageperformancegotocode.png "FFR_ITSummaryPagePerformanceGoToCode")  
  
     Teď můžete zkontrolovat ostatní zaznamenaná hodnoty, zásobník volání krokovat kód, nebo použijte **IntelliTrace** okna [přesunout zpětné nebo dopředný "v čase" mezi jiné metody](../debugger/intellitrace.md) byly během volat Tato událost výkonu.  
  
###  <a name="ExceptionData"></a> Data výjimky  
 Zkontrolujte výjimky, které byly vyvolány a zaznamenává pro vaši aplikaci. Můžete seskupit výjimky, které mají stejného typu a, abyste viděli pouze poslední výjimka zásobník volání.  
  
##### <a name="to-start-debugging-from-an-exception"></a>Spustit ladění z výjimku  
  
1.  V části **Data výjimky**, zkontrolujte události zaznamenané výjimky, jejich typy, zprávy, a když se stalo výjimky. Pokud se chcete dostat hlouběji do kódu, spusťte ladění od poslední události ve skupině výjimek.  
  
     ![Spuštění ladění ze události výjimky](../debugger/media/ffr_itsummarypageexception.png "FFR_ITSummaryPageException")  
  
     Můžete také pouze dvakrát kliknout na událost. Pokud nejsou seskupeny události, zvolte **ladění Tato událost**.  
  
     Pokud došlo k výjimce v kódu aplikace, sada Visual Studio pokračuje tam, kde došlo k výjimce.  
  
     ![Přejděte do kódu aplikace z události výjimky](../debugger/media/ffr_itsummarypageexceptiongotocode.png "FFR_ITSummaryPageExceptionGoToCode")  
  
     Teď můžete zkontrolovat ostatní zaznamenaná hodnoty, zásobník volání, nebo můžete použít **IntelliTrace** okna [přesunout zpětné nebo dopředný "v čase" mezi další zaznamenané události](../debugger/intellitrace.md), související kód a zaznamenají na hodnoty Tyto body v čase.  
  
    |**Sloupec**|**Zobrazuje**|  
    |----------------|-------------------|  
    |**Typ**|Typ formátu .NET výjimky|  
    |**Nejnovější zpráva** pro seskupené výjimky nebo **zpráva** Neseskupená výjimky|Zpráva poskytované výjimka|  
    |**Počet** pro seskupené výjimky|Počet, z níž byla výjimka|  
    |**ID podprocesu** Neseskupená výjimky|ID podprocesu, která vrátila výjimku|  
    |**Nejnovější čas události** nebo **čas události**|Časové razítko zaznamenávají, když byla vyvolána výjimka|  
    |**Zásobník volání**|Volání zásobníku pro výjimku.<br /><br /> Zásobník volání najdete v seznamu vyberte výjimku. Zásobník volání se zobrazí pod seznamu výjimek.|  
  
###  <a name="Analysis"></a> Analýza  
 Diagnostikovat problémy s aplikací SharePoint 2010 a SharePoint 2013 pomocí služby SharePoint korelační ID nebo zkontrolujte všechny neošetřené výjimky, které nalezen agenta Microsoft Monitoring Agent.  
  
-   Pomocí ID korelace SharePoint najít jeho odpovídající webové žádosti a události. Vyberte události a pak spusťte ladění v místě, kde a kdy k události došlo.  
  
-   Pokud agenta Microsoft Monitoring Agent nalezen neošetřených výjimek, vyberte výjimku a pak spusťte ladění v místě, kde a kdy došlo k výjimce.  
  
##### <a name="start-debugging-with-a-sharepoint-correlation-id"></a>Spuštění ladění s ID korelace SharePoint  
  
1.  Zkopírujte ID korelace služby SharePoint z její zdroj.  
  
     Příklad:  
  
     ![IntelliTrace &#45; chybu služby SharePoint &#45; ID korelace](../debugger/media/sharepointerror_intellitrace.png "SharePointError_IntelliTrace")  
  
2.  Otevřete soubor .iTrace a potom přejděte na **Analysis** a zadejte ID korelace SharePoint ke kontrole odpovídající webový požadavek a zaznamenává události.  
  
     ![Protokolu IntelliTrace &#45; ID korelace zadejte SharePoint](../debugger/media/entersharepointcorrelationid.png "EnterSharePointCorrelationID")  
  
3.  V části **žádosti o události**, zkontrolujte události. Od horní, události se zobrazí v pořadí, že při jejich vzniku.  
  
    1.  Zvolte událost zobrazíte její podrobnosti.  
  
    2.  Zvolte **spustit ladění** spustit ladění – v okamžiku, kdy k události došlo.  
  
     ![Soubor protokolu IntelliTrace &#45; zobrazení webové žádosti &#43; události](../debugger/media/entersharepointcorrelationid2.png "EnterSharePointCorrelationID2")  
  
 Zobrazí se tyto druhy událostí SharePoint společně s události IntelliTrace:  
  
-   **Události profilu uživatele**  
  
     Tyto události dojít, když SharePoint načte uživatelský profil a když jsou přečteny nebo změnit vlastnosti profilu uživatele.  
  
-   **Jednotná události protokolování systému (ULS)**  
  
     Microsoft Monitoring Agent zaznamenává podmnožinu události ULS služby SharePoint a tato pole:  
  
    |**Pole IntelliTrace**|**Pole ULS služby SharePoint**|  
    |----------------------------|------------------------------|  
    |**ID**|**ID události**|  
    |**úroveň**|**úroveň**|  
    |**Kategorie Id**|**Kategorie Id**|  
    |**Kategorie**|**Kategorie**|  
    |**Oblasti**|**Produktu**|  
    |**Output**|**Zpráva**|  
    |**Id korelace**|**Id korelace**|  
  
##### <a name="start-debugging-from-an-unhandled-exception"></a>Spuštění ladění z nezpracované výjimky  
  
1.  Zvolte SharePoint korelační ID pro výjimku. Výjimky jsou seskupeny podle typu a zásobník volání.  
  
2.  (Volitelné) Rozbalte položku **zásobníkem volání** zobrazíte zásobníku volání pro skupinu výjimek.  
  
3.  Zvolte **ladění výjimka** spustit ladění – v místě, kde a kdy došlo k výjimce.  
  
     ![Protokolu IntelliTrace &#45; SharePoint neošetřené výjimky](../debugger/media/sharepointunhandledexceptions_intellitrace.png "SharePointUnhandledExceptions_IntelliTrace")  
  
 Podrobný postup najdete v části [návod: ladění aplikace SharePoint pomocí IntelliTrace pomocí](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md). Pro různé druhy dat, která najdete v části záznamy agent [funkce IntelliTrace](../debugger/intellitrace-features.md).  
  
###  <a name="ThreadsList"></a> Seznam vláken  
 Zkontrolujte zaznamenaná vláken, které byly spuštěny v tento cílový proces. Můžete spustit ladění z první platný události IntelliTrace ve vybrané vlákno.  
  
##### <a name="to-start-debugging-from-a-specific-thread"></a>Spustit ladění z konkrétní vlákna  
  
1.  V části **seznamu vláken**, zvolte vlákna.  
  
2.  V dolní části **vláken seznamu**, zvolte **spustit ladění**. Klikněte dvakrát na vlákno.  
  
     Chcete-li spustit ladění z kde aplikace začne, dvakrát klikněte na **vláken hlavní**. V tématu [funkce IntelliTrace](../debugger/intellitrace-features.md).  
  
 Data přístup z více vláken, která uživatel vytvoří může být užitečnější než vláken, které server vytváří a spravuje pro hostované službou IIS webové aplikace.  
  
|**Sloupec**|**Zobrazuje**|  
|----------------|-------------------|  
|**ID**|Číslo ID vlákna|  
|**Jméno**|Název vlákna. Nepojmenované vláken zobrazí jako "\<bez názvu >".|  
|**Čas spuštění**|Čas vytvoření vlákna|  
|**Koncový čas**|Čas, kdy vlákno bylo dokončeno.|  
  
###  <a name="TestData"></a> Testovacích dat  
 Zkontrolujte dat technologie IntelliTrace, který nástroje Test Manager poznamenali při testování vaší aplikace.  
  
##### <a name="to-start-debugging-from-a-specific-test-step"></a>Spustit ladění z kroku specifický test  
  
1.  Rozbalte položku **testovací kroky mřížky**. Zvolte test krok.  
  
2.  V dolní části **mřížky kroky testu**, zvolte **spustit ladění**. Klikněte dvakrát na test krok.  
  
     Tím se spustí po kroku vybrané zkušební ladění z první platný události IntelliTrace.  
  
     Pokud existuje testovací data, IntelliTrace se pokusí přeložit přidružené sestavení Team Foundation Server, který byl použit k provedení testovacím běhu. Pokud je nalezen sestavení, jsou automaticky vyřešen přidružené symboly pro aplikaci.  
  
|**Pole**|**Zobrazuje**|  
|---------------|-------------------|  
|**Relace testu**|Otestujte relací, které nebyly zaznamenány. Obvykle je jen jeden. Tento seznam je prázdný, pokud testovací data byla vytvořena pomocí ruční nahodilého testu.|  
|**Testovacího případu**|Testovacích případů z relace vybrané testu. Tento seznam je prázdný, pokud testovací data byla vytvořena pomocí ruční nahodilého testu.|  
|**Testovací kroky mřížky**|Kroky, které byly zapsány s výsledků testů průchodu testů nebo selhání|  
  
###  <a name="SystemInfo"></a> Informace o systému  
 Tato část uvádí podrobnosti o systému, který hostuje aplikaci, například hardwaru, operačního systému, informace o prostředí a specifické pro proces.  
  
###  <a name="Modules"></a> Moduly  
 Tato část uvádí moduly, které tento cílový proces načíst. Moduly se zobrazí v pořadí, ve kterém budou načteny.  
  
|**Sloupec**|**Zobrazuje**|  
|----------------|-------------------|  
|**Název modulu**|Název souboru modulu|  
|**Cesta modulu**|Umístění disku, kde byl načten modulu|  
|**ID modulu**|Jedinečný identifikátor modul, který je specifické pro verzi a přispívá k odpovídající soubory symbolů (PDB). V tématu [hledání souborů symbolu (.pdb) a zdrojové soubory](http://msdn.microsoft.com/en-us/05384c85-d264-4e18-abaa-aa482ab25470).|  
  
### <a name="where-can-i-get-more-information"></a>Kde lze získat další informace?  
 [Použití samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md)  
  
 [Funkce IntelliTrace](../debugger/intellitrace-features.md)  
  
 [Shromažďování více diagnostických dat v manuálních testech](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)  
  
 [IntelliTrace](../debugger/intellitrace.md)  
  
#### <a name="forums"></a>Diskuzní fóra  
 [Ladicí program Visual Studio](http://go.microsoft.com/fwlink/?LinkId=262263)  
  
#### <a name="guidance"></a>Doprovodné materiály  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 6: testování sady nástrojů](http://go.microsoft.com/fwlink/?LinkID=255203)