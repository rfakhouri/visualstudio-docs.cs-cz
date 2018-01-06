---
title: "Použití služby Microsoft Monitoring Agent. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0a86b9-015d-408e-aa58-59a0a97826ac
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3e5963568eac26e7f88acf3ba07466fd1261eed1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-microsoft-monitoring-agent"></a>Použití služby Microsoft Monitoring Agent
Místně můžete monitorovat webové aplikace ASP.NET hostované službou IIS a služby SharePoint 2010 nebo 2013 aplikací pro chyby, problémy s výkonem nebo jiné problémy pomocí **agenta Microsoft Monitoring Agent**. Diagnostické události od agenta můžete uložit do souboru protokolu (.iTrace) IntelliTrace. V protokolu pak můžete otevřít ve Visual Studio Enterprise (ale ne edice Professional nebo komunity) pro ladění problémů s všechny diagnostické nástroje sady Visual Studio. Může taky shromažďovat diagnostická data IntelliTrace a metoda data spuštěním agenta v **trasování** režimu. Microsoft Monitoring Agent lze integrovat s [Application Insights](http://www.visualstudio.com/get-started/find-performance-problems-vs.aspx) a [System Center Operation Manager](http://technet.microsoft.com/library/hh205987.aspx). Microsoft Monitoring Agent změnit prostředí cílového systému, když je nainstalovaná.  
  
> [!NOTE]
>  Může taky shromažďovat data diagnostiky a metoda IntelliTrace pro webový server, SharePoint, WPF a formuláře aplikací pro Windows na vzdálených počítačích beze změny cílové prostředí pomocí **samostatné kolekce IntelliTrace**. Samostatné kolekce má dopad na vyšší výkon než Microsoft Monitoring Agent spuštěný **monitorování** režimu. V tématu [pomocí samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md).  
  
 Pokud používáte System Center 2012, použijte k získání výstrah o problémech a vytváření pracovních položek sady Team Foundation Server s odkazy na uložené protokoly IntelliTrace agenta Microsoft Monitoring Agent s nástrojem Operations Manager. Pak tyto můžete přiřadit pracovní položky pro ostatní pro další ladění. V tématu [integrace nástroje Operations Manager s procesy vývoje](http://technet.microsoft.com/library/jj614609.aspx) a [monitorování pomocí aplikace Microsoft Monitoring Agent](http://technet.microsoft.com/en-us/library/dn465153.aspx).  
  
 Než začnete, zkontrolujte, že máte odpovídající zdroj a symboly pro kód vytvořené a nasazené. Díky tomu můžete přejít přímo na kód aplikace při spuštění ladění a procházení diagnostických událostí v protokolu IntelliTrace. [Nastavit buildy](../debugger/diagnose-problems-after-deployment.md) tak, aby v sadě Visual Studio můžete automaticky najít a otevřít odpovídající zdroj nasazené kódu.  
  
1.  [Krok 1: Nastavení agenta Microsoft Monitoring Agent](#SetUpMonitoring)  
  
2.  [Krok 2: Spuštění monitorování aplikace](#MonitorEvents)  
  
3.  [Krok 3: Uložení zaznamenané události](#SaveEvents)  
  
##  <a name="SetUpMonitoring"></a>Krok 1: Nastavení agenta Microsoft Monitoring Agent  
 Nastavení agenta samostatné na vašem webovém serveru k provedení místní monitorování beze změny aplikace. Pokud používáte System Center 2012, najdete v části [instalaci agenta Microsoft Monitoring Agent](http://technet.microsoft.com/library/dn465156.aspx).  
  
###  <a name="SetUpStandaloneMMA"></a>Nastavte samostatnou agenta  
  
1.  Ujistěte se, že:  
  
    -   Váš webový server je spuštěna [podporované verze Internetové informační služby (IIS)](http://technet.microsoft.com/en-us/library/dn465154.aspx).  
  
    -   Váš webový server má rozhraní .NET Framework 3.5, 4 nebo 4.5.  
  
    -   Váš webový server používá prostředí Windows PowerShell 3.0 nebo novější. [Otázka: Co když je nutné prostředí Windows PowerShell 2.0?](#PowerShell2)  
  
    -   Mít oprávnění správce na vašem webovém serveru ke spuštění příkazů prostředí PowerShell a recyklace fondu aplikací při spuštění monitorování.  
  
    -   Jste odinstalovat všechny starší verze služby Microsoft Monitoring Agent.  
  
2.  [Stáhněte si bezplatnou Microsoft Monitoring Agent](http://go.microsoft.com/fwlink/?LinkId=320384), 32bitová verze **MMASetup-i386.exe** nebo 64bitovou verzi **MMASetup-AMD64.exe**, z webu Microsoft Download Center do webového Server.  
  
3.  Spusťte stažený spustitelného souboru pro spuštění Průvodce instalací.  
  
4.  Vytvoření zabezpečeného adresáře na webovém serveru k ukládání protokolů IntelliTrace, například **C:\IntelliTraceLogs**.  
  
     Zajistěte, aby tento adresář vytvořit před zahájením monitorování. Abyste se vyhnuli zpomalení vaší aplikace, vyberte umístění na místním disku vysokorychlostní, který není velmi aktivní.  
  
    > [!IMPORTANT]
    >  Protokoly nástroje IntelliTrace může obsahovat osobní a citlivé data. Tento adresář omezte pouze identitám, které musíte pracovat se soubory. Zkontrolujte zásady ochrany osobních údajů vaší společnosti.  
  
5.  Ke spuštění podrobné, úroveň funkci monitorování nebo k monitorování aplikací služby SharePoint, měl fond aplikací, který je hostitelem vaší webové aplikace nebo aplikace SharePoint oprávnění čtení a zápisu do adresáře protokolu IntelliTrace. [Otázka: Jak mám nastavit oprávnění pro fond aplikací?](#FullPermissionsITLog)  
  
### <a name="q--a"></a>Dotazy a odpovědi  
  
####  <a name="PowerShell2"></a>Otázka: Co když je nutné prostředí Windows PowerShell 2.0?  
 **Odpověď:** důrazně doporučujeme použít PowerShell 3.0. Jinak budete muset importovat rutin prostředí PowerShell agenta monitorování Microsoft pokaždé, když spustit prostředí PowerShell. Také nebudete mít přístup k dispozici ke stažení obsahu nápovědy.  
  
1.  Otevřete **prostředí Windows PowerShell** nebo **Windows PowerShell ISE** okno příkazového řádku jako správce.  
  
2.  Importujte modul PowerShell agenta monitorování Microsoft z výchozí umístění instalace:  
  
     **PS C: > Import-Module "C:\Program Files\Microsoft Monitoring Agent\Agent\PowerShell\Microsoft.MonitoringAgent.PowerShell\Microsoft.MonitoringAgent.PowerShell.dll"**  
  
3.  [Navštivte TechNet](http://technet.microsoft.com/systemcenter/default) získat nejaktuálnějšího obsahu nápovědy.  
  
####  <a name="FullPermissionsITLog"></a>Otázka: Jak mám nastavit oprávnění pro fond aplikací?  
 **Odpověď:** použití Windows **icacls** příkaz nebo pomocí Průzkumníka Windows (nebo Průzkumníka souborů). Příklad:  
  
-   Nastavit oprávnění s Windows **icacls** příkaz:  
  
    -   Pro webovou aplikaci v **DefaultAppPool** fondu aplikací:  
  
         `icacls "C:\IntelliTraceLogs" /grant "IIS APPPOOL\DefaultAppPool":RX`  
  
    -   Pro aplikaci služby SharePoint v **SharePoint - 80** fondu aplikací:  
  
         `icacls "C:\IntelliTraceLogs" /grant "IIS APPPOOL\SharePoint - 80":RX`  
  
     -nebo-  
  
-   Nastavení oprávnění pro Průzkumníka Windows (nebo v Průzkumníku souborů):  
  
    1.  Otevřete **vlastnosti** pro adresář protokolu IntelliTrace.  
  
    2.  Na **zabezpečení** , zvolte **upravit**, **přidat**.  
  
    3.  Ujistěte se, že **předdefinované objekty zabezpečení** se zobrazí v **vyberte tento typ objektu** pole. Pokud se má existuje, volbu **typy objektů** ho přidejte.  
  
    4.  Ujistěte se, že se zobrazí v místním počítači **z tohoto umístění** pole. Pokud se má existuje, volbu **umístění** ho změnit.  
  
    5.  V **zadejte názvy objektů k výběru** pole, přidat fond aplikací pro webovou aplikaci nebo aplikaci služby SharePoint.  
  
    6.  Zvolte **Kontrola názvů** přeložit název. Zvolte **OK**.  
  
    7.  Ověřte, zda fond aplikací má **čtení & Spustit** oprávnění.  
  
##  <a name="MonitorEvents"></a>Krok 2: Spuštění monitorování aplikace  
 Pomocí prostředí Windows PowerShell [Start-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313686) příkaz ke spuštění monitorování vaší aplikace. Pokud používáte System Center 2012, najdete v části [monitorování webových aplikací pomocí agenta Microsoft Monitoring Agent](http://technet.microsoft.com/library/dn465157.aspx).  
  
1.  Na vašem webovém serveru, otevřete **prostředí Windows PowerShell** nebo **Windows PowerShell ISE** okno příkazového řádku jako správce.  
  
     ![Otevřete prostředí Windows PowerShell jako správce](../debugger/media/ffr_powershellrunadmin.png "FFR_PowerShellRunAdmin")  
  
2.  Spustit [Start-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313686) příkaz ke spuštění monitorování vaší aplikace. To se restartuje všechny webové aplikace na vašem webovém serveru.  
  
     Tady je krátký syntaxe:  
  
     **Start-WebApplicationMonitoring** *"\<appName >"*  *\<monitoringMode >* *"\<outputPath >"*  *\<UInt32 >* *"\<collectionPlanPathAndFileName >"*  
  
     Tady je příklad, který používá jenom název webové aplikace a lightweight **monitorování** režimu:  
  
     **PS C: > Start-WebApplicationMonitoring "FabrikamFabrikamFiber.Web" sledovat "C:IntelliTraceLogs"**  
  
     Tady je příklad, který používá cesta služby IIS a lightweight **monitorování** režimu:  
  
     **PS C: > Start-WebApplicationMonitoring "IIS:sitesFabrikamFabrikamFiber.Web" sledovat "C:IntelliTraceLogs"**  
  
     Po spuštění monitorování, můžete se setkat agenta Microsoft Monitoring Agent pozastavení při restartování aplikace.  
  
     ![Zahájení monitorování MMA potvrzení](../debugger/media/ffr_powershellstartmonitoringconfirmation.png "FFR_PowerShellStartMonitoringConfirmation")  
  
    |||  
    |-|-|  
    |*"\<appName >"*|Zadejte cestu k název webu a webové aplikace ve službě IIS. Můžete taky zahrnout cestu ke službě IIS, pokud dáváte přednost.<br /><br /> *"\<IISWebsiteName >\\< IISWebAppName\>"*<br /><br /> -nebo-<br /><br /> **"IIS:\sites**  *\\< IISWebsiteName\>\\< IISWebAppName\>"*<br /><br /> Tuto cestu můžete najít ve Správci služby IIS. Příklad:<br /><br /> ![Cesta k webu služby IIS a webové aplikace](../debugger/media/ffr_iismanager.png "FFR_IISManager")<br /><br /> Můžete také [Get-WebSite](http://technet.microsoft.com/library/ee807832.aspx) a [získat WebApplication](http://technet.microsoft.com/library/ee790554.aspx) příkazy.|  
    |*\<monitoringMode >*|Zadejte režim monitorování:<br /><br /> <ul><li>**Monitorování**: záznam minimální podrobnosti o události výjimky a událostí výkonu. Tento režim použije výchozí plán kolekce.</li><li>**Trasování**: zaznamenejte podrobnosti na úrovni funkce nebo monitorování aplikací služby SharePoint 2010 a SharePoint 2013 pomocí plán zadané kolekci. Tento režim může být aplikace spuštění pomaleji.<br /><br /> <ul><li>[Otázka: Jak mám nastavit oprávnění pro fond aplikací?](#FullPermissionsITLog)</li><li>[Otázka: Jak získat většinu dat bez zpomalení mé aplikace?](#Minimizing)</li></ul><br />     Tento příklad zaznamenává události pro aplikaci SharePoint hostované na webu služby SharePoint:<br /><br />     **Start-WebApplicationMonitoring "FabrikamSharePointSite\FabrikamSharePointApp" trasování C:\IntelliTraceLogs""C:\Program Files\Microsoft Monitoring Agent\Agent\IntelliTraceCollector\collection_plan.ASP.NET.default.xml""**</li><li>**Vlastní**: zaznamenání vlastní podrobnosti pomocí zadané kolekce vlastní plán. Budete muset restartovat, monitorování, pokud chcete upravit plán kolekcí po monitorování již bylo zahájeno.</li></ul>|  
    |*"\<outputPath >"*|Zadejte cestu úplné adresáře k ukládání protokolů IntelliTrace. Zajistěte, aby tento adresář vytvořit před zahájením monitorování.|  
    |*\<UInt32 >*|Zadejte maximální velikost protokolu IntelliTrace. Výchozí maximální velikost protokolu IntelliTrace je 250 MB.<br /><br /> Když dosáhne tento limit, přepíše agenta Nejdřívější položkách, které chcete uvolnit místo pro další položky. Chcete-li tento limit změnit, použijte **- MaximumFileSizeInMegabytes** možnost nebo upravit `MaximumLogFileSize` atribut v plánu kolekce.|  
    |*"\<collectionPlanPathAndFileName >"*|Zadejte úplnou cestu nebo relativní cestu a název souboru nebo plán kolekce. Tento plán je soubor .xml, který konfiguruje nastavení pro agenta.<br /><br /> Tyto plány jsou součástí agenta a práce s webovými aplikacemi a aplikací služby SharePoint:<br /><br /> -   **collection_plan.ASP.NET.default.XML**<br />     Shromažďuje jenom události, jako je například výjimky, události výkonu, volání databáze a požadavky webový server.<br />-   **collection_plan.ASP.NET.Trace.XML**<br />     Volání funkce úroveň shromažďuje a všechna data v výchozí plán kolekce. Tento plán je vhodný pro podrobné analýzy, ale může zpomalit vaší aplikace.<br /><br /> Lokalizované verze těchto plánech můžete najít v podsložkách agenta. Můžete také [přizpůsobit tyto plány nebo vytvářet vlastní plány](http://go.microsoft.com/fwlink/?LinkId=227871) předejdete zpomalení vaší aplikace. Uveďte všechny vlastní plány ve stejném zabezpečené umístění jako agenta.<br /><br /> [Otázka: Jak získat většinu dat bez zpomalení mé aplikace?](#Minimizing)|  
  
     Další informace o úplnou syntaxí a další příklady, spusťte **get-help Start-WebApplicationMonitoring-podrobné** příkaz nebo **get-help Start-WebApplicationMonitoring-příklady** příkaz.  
  
3.  Chcete-li zkontrolovat stav všech monitorovat webové aplikace, spusťte [Get-WebApplicationMonitoringStatus](http://go.microsoft.com/fwlink/?LinkID=313685) příkaz.  
  
### <a name="q--a"></a>Dotazy a odpovědi  
  
####  <a name="Minimizing"></a>Otázka: Jak získat většinu dat bez zpomalení mé aplikace?  
 **Odpověď:** agenta Microsoft Monitoring Agent může shromažďovat velké množství dat a ovlivňuje výkon vaší aplikace v závislosti na data, která chcete shromažďovat a jak shromáždit. Tady jsou některé způsoby, jak získat většinu dat bez zpomalení aplikace:  
  
-   Pro webové aplikace a aplikací služby SharePoint agent zaznamenává data pro každou aplikaci, která sdílí zadaný fond aplikací. Může dojít ke zpomalení jakékoli aplikaci, která sdílí stejný fond aplikací, i když můžete omezit kolekce modulů pro jednu aplikaci. Abyste se vyhnuli zpomalením z jiných aplikací, hostitel každou aplikaci ve vlastním fondu aplikací.  
  
-   Kontrolujte události, pro které agent shromažďuje data v plánu kolekce. Upravte plán kolekce zakázat události, které nejsou relevantní, nebo nemáte vás zajímají. Tím lze vylepšit výkon při spuštění a výkon modulu runtime.  
  
     Chcete-li zakázat událost, nastavte `enabled` atribut pro `<DiagnosticEventSpecification>` elementu, který chcete `false`:  
  
     `<DiagnosticEventSpecification enabled="false">`  
  
     Pokud `enabled` atribut neexistuje, je událost povolena.  
  
     Příklad:  
  
    -   Zakážete události pracovního postupu systému Windows pro aplikace, které nepoužívají Windows Workflow.  
  
    -   Zakážete události registru pro aplikace, které přístup do registru, ale nezobrazovat problémy s nastavením registru.  
  
-   Zkontrolujte moduly, pro které agent shromažďuje data v plánu kolekce. Upravte plán kolekce zahrnout pouze moduly, které vás zajímají.  
  
     Tím se snižuje množství informací volání metoda a dalších dat instrumentace, které agent shromažďuje při spuštění a spuštění aplikace. Tato data pomáhá při ladění a kontrola hodnoty předané do a vrácená z volání funkce krok prostřednictvím kódu.  
  
    1.  Otevřete plán kolekcí. Najít `<ModuleList>` elementu.  
  
    2.  V `<ModuleList>`, nastavte `isExclusionList` atribut `false`.  
  
    3.  Použití `<Name>` elementu, který chcete určit každý modul s jedním z následujících akcí: název souboru, řetězcovou hodnotu zahrnout libovolný modul, jejichž název obsahuje tento řetězec nebo veřejný klíč.  
  
     Tento příklad vytvoří seznam, který shromažďuje data pouze z hlavní modul Fabrikam Fiber webové aplikace:  
  
    ```xml  
    <ModuleList isExclusionList="false">  
       <Name>FabrikamFiber.Web.dll</Name>  
    </ModuleList>  
  
    ```  
  
     Ke shromažďování dat z jakékoli modulu, jehož název obsahuje "Fabrikam", vytvořte seznam podobné následujícímu:  
  
    ```xml  
    <ModuleList isExclusionList="false">  
       <Name>Fabrikam</Name>  
    </ModuleList>  
  
    ```  
  
     Ke shromažďování dat z modulů zadáním jejich tokenů veřejných klíčů, vytvořte seznam podobné následujícímu:  
  
    ```xml  
    <ModuleList isExclusionList="false">  
       <Name>PublicKeyToken:B77A5C561934E089</Name>  
       <Name>PublicKeyToken:B03F5F7F11D50A3A</Name>  
       <Name>PublicKeyToken:31BF3856AD364E35</Name>  
       <Name>PublicKeyToken:89845DCD8080CC91</Name>  
       <Name>PublicKeyToken:71E9BCE111E9429C</Name>  
    </ModuleList>  
  
    ```  
  
     **Otázka: Proč není právě vyloučit moduly místo?**  
  
     **Odpověď:** ve výchozím nastavení, plány kolekce vyloučit moduly nastavením `isExclusionList` atribut `true`. Ale to může stále shromažďovat data z modulů, které nesplňují kritéria v seznamu nebo, nemusí zajímají, jako je například modulů třetích stran nebo open source.  
  
#### <a name="q-what-values-does-the-agent-collect"></a>Otázka: co hodnoty podporuje shromažďování agenta?  
 **Odpověď:** pro snížení vlivu na výkon, agent shromažďuje pouze tyto hodnoty:  
  
-   Primitivní datové typy, které jsou předána do a byla vrácena z metody  
  
-   Primitivní datové typy v polích pro nejvyšší úrovně objekty předal a byla vrácena z metody  
  
 Předpokládejme například, že máte `AlterEmployee` podpis metody, který přijímá celé `id` a `Employee` objekt `oldemployee`:  
  
 `public Employee AlterEmployee(int id, Employee oldemployee)`  
  
 `Employee` Typ má následující atributy: `Id`, `Name`, a `HomeAddress`. Přidružení vztah mezi `Employee` a `Address` typu.  
  
 ![Vztah mezi zaměstnanci a adresu](../debugger/media/employeeaddressrelationship.png "EmployeeAddressRelationship")  
  
 Agent zaznamenává hodnoty pro `id`, `Employee.Id`, `Employee.Name` a `Employee` objekt vrácený `AlterEmployee` metoda. Však není agent zaznamenejte informace o `Address` objektu, než bez ohledu na jeho, jestli byla null. Agent také nezaznamená data o místní proměnné v `AlterEmployee` metoda Pokud jiné metody použít tyto místní proměnné jako parametry v tomto okamžiku se zaznamenávají jako parametry metody.  
  
##  <a name="SaveEvents"></a>Krok 3: Uložení zaznamenané události  
 Při najdete chybu nebo problém s výkonem, uložte zaznamenaná události do protokolu IntelliTrace. Agent vytvoří protokol pouze v případě, že se zaznamenávají události. Pokud používáte System Center 2012, najdete v části [monitorování webových aplikací pomocí agenta Microsoft Monitoring Agent](http://technet.microsoft.com/library/dn465157.aspx).  
  
### <a name="save-recorded-events-but-continue-monitoring"></a>Uložení zaznamenané události, ale pokračovat v monitorování  
 Pokud chcete vytvořit protokolu IntelliTrace, ale nechcete, aby se aplikace znovu spustit nebo zastavit monitorování, postupujte podle těchto kroků. Agent bude pokračovat v monitorování i v případě restartování serveru nebo aplikaci.  
  
1.  Na vašem webovém serveru otevřete okno příkazového řádku prostředí Windows PowerShell jako správce.  
  
2.  Spustit [Checkpoint-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313684) příkazu uložte snímek IntelliTrace protokolu:  
  
     **Checkpoint-WebApplicationMonitoring** *"\<IISWebsiteName >\\< IISWebAppName\>"*  
  
     \-nebo –  
  
     **Checkpoint-WebApplicationMonitoring "IIS:\sites**  *\\< IISWebsiteName\>\\< IISWebAppName\>"*  
  
     Příklad:  
  
     **PS C:\\> Checkpoint-WebApplicationMonitoring "Fabrikam\FabrikamFiber.Web"**  
  
     -nebo-  
  
     **PS C: > Checkpoint-WebApplicationMonitoring "IIS:sitesFabrikamFabrikamFiber.Web"**  
  
     Další informace získáte spuštěním **get-help Checkpoint-WebApplicationMonitoring-podrobné** příkaz nebo **get-help Checkpoint-WebApplicationMonitoring-příklady** příkaz.  
  
3.  Zkopírovat protokol do zabezpečené sdílené složky a pak otevřete protokol z počítače, který má Visual Studio Enterprise (ale ne edice Professional nebo komunity).  
  
    > [!IMPORTANT]
    >  Buďte opatrní při sdílení protokoly IntelliTrace, protože mohou obsahovat osobní a citlivá data. Ujistěte se, kdo může těmto protokolům získat přístup má oprávnění k podívejte se na tato data. Zkontrolujte zásady ochrany osobních údajů vaší společnosti.  
  
 **Další krok:** [Diagnostikujte zaznamenávají události Visual Studio Enterprise](../debugger/diagnose-problems-after-deployment.md#InvestigateEvents)  
  
### <a name="save-recorded-events-and-stop-monitoring"></a>Uložit zaznamenaná události a zastavit monitorování  
 Pokud chcete k získání diagnostických informací při reprodukci určitý problém, postupujte takto. To se restartuje všechny webové aplikace na vašem webovém serveru.  
  
1.  Na vašem webovém serveru otevřete okno příkazového řádku prostředí Windows PowerShell jako správce.  
  
2.  Spustit [Stop-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313687) příkaz pro vytvoření protokolu IntelliTrace a zastavit monitorování konkrétní webové aplikace:  
  
     **Příkaz Stop-WebApplicationMonitoring** *"\<IISWebsiteName >\\< IISWebAppName\>"*  
  
     \-nebo –  
  
     **Příkaz Stop-WebApplicationMonitoring "IIS:\sites**  *\\< IISWebsiteName\>\\< IISWebAppName\>"*  
  
     Nebo zastavit monitorování všech webových aplikací:  
  
     **Příkaz Stop-WebApplicationMonitoring - všechny**  
  
     Příklad:  
  
     **PS C:\\> Stop-WebApplicationMonitoring "Fabrikam\iFabrikamFiber.Web"**  
  
     \-nebo –  
  
     **PS C:\\> Stop-WebApplicationMonitoring "IIS:\sites\Fabrikam\FabrikamFiber.Web"**  
  
     Další informace získáte spuštěním **get-help Stop-WebApplicationMonitoring-podrobné** příkaz nebo **get-help Stop-WebApplicationMonitoring-příklady** příkaz.  
  
3.  Zkopírovat protokol do zabezpečené sdílené složky a pak otevřete protokol z počítače, který má Visual Studio Enterprise.  
  
 **Další krok:** [Diagnostikujte zaznamenávají události Visual Studio Enterprise](../debugger/diagnose-problems-after-deployment.md#InvestigateEvents)  
  
## <a name="q--a"></a>Dotazy a odpovědi  
  
### <a name="q-where-can-i-get-more-information"></a>Otázka: kde je můžete získat další informace?  
  
#### <a name="blogs"></a>Blogy  
 [Představujeme službu Microsoft Monitoring Agent.](http://blogs.msdn.com/b/visualstudioalm/archive/2013/09/20/introducing-microsoft-monitoring-agent.aspx)  
  
 [Optimalizace shromažďování snímků IntelliTrace na provozních serverech](http://go.microsoft.com/fwlink/?LinkId=255233)  
  
#### <a name="forums"></a>Diskuzní fóra  
 [Diagnostika sady Visual Studio](http://go.microsoft.com/fwlink/?LinkId=262263)