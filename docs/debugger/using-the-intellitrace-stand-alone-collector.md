---
title: "Použití samostatného kolektoru IntelliTrace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.historicaldebug.collectdataoutsideVS
helpviewer_keywords: IntelliTrace, debugging applications in production
ms.assetid: 1bde9807-8219-4a2a-a440-ac5ee5178159
caps.latest.revision: "105"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29f87ccebc342e6b5b03d40aab789ff80496a96d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="using-the-intellitrace-stand-alone-collector"></a>Použití samostatného kolektoru IntelliTrace
**Samostatné kolekce IntelliTrace** umožňuje shromažďování diagnostických dat technologie IntelliTrace pro vaše aplikace na produkční servery nebo jiných prostředích bez instalace sady Visual Studio na cílovém počítači a beze změny cílové prostředí systému. V aplikacích WPF a Windows Forms web, SharePoint, lze použít samostatné kolekce IntelliTrace. Po dokončení shromažďování dat, stačí odstraňte kolekce ho odinstalovat.  
  
 Podívejte se na IntelliTrace v akci: [shromažďování a analýzy dat technologie IntelliTrace v produkčním prostředí pro ladění (video na kanálu 9)](http://go.microsoft.com/fwlink/?LinkID=251851)  
  
> [!NOTE]
>  Může taky shromažďovat stejné dat technologie IntelliTrace pro web a SharePoint aplikace běžící na vzdálených počítačích pomocí **agenta Microsoft Monitoring Agent** v **trasování** režimu.  
>   
>  Můžete shromažďovat události související s výkonem v dat technologie IntelliTrace, kterém je spuštěn agent **monitorování** režimu. **Monitorování** režim má menší dopad na výkon než **trasování** režimu nebo **samostatné kolekce IntelliTrace**. Microsoft Monitoring Agent změnit prostředí cílového systému, když je nainstalovaná. V tématu [pomocí agenta Microsoft Monitoring Agent](../debugger/using-the-microsoft-monitoring-agent.md).  
  
 **Požadavky**  
  
-   Rozhraní .NET framework 3.5, 4 nebo 4.5  
  
-   Visual Studio Enterprise (ale ne Professional nebo komunity edice) na vývojovém počítači nebo jinému počítači otevřít soubory .iTrace  
  
    > [!NOTE]
    >  Ujistěte se, že uložit vaše symbolu (.pdb) soubory. Ladění pomocí technologie IntelliTrace a krok prostřednictvím kódu, musí mít odpovídající zdrojové soubory a soubory symbolů. V tématu [Diagnostika problémů po nasazení](../debugger/diagnose-problems-after-deployment.md).  
  
 **NEJČASTĚJŠÍ DOTAZY**  
  
-   [Které aplikace podporují kolekce?](#WhatApps)  
  
-   [Jak můžu začít pracovat?](#GetStarted)  
  
-   [Načtení většinu dat bez zpomalení mé aplikace?](#Minimizing)  
  
-   [Jinak kde může získat dat technologie IntelliTrace?](#WhereElse)  
  
##  <a name="WhatApps"></a>Které aplikace podporují kolekce?  
  
-   ASP.NET – webové aplikace hostované na Internetové informační služby (IIS) verze 7.0, 7.5 a 8.0  
  
-   Aplikace služby SharePoint 2010 a SharePoint 2013  
  
-   Windows Presentation Foundation (WPF) a Windows Forms aplikace.  
  
##  <a name="GetStarted"></a>Jak můžu začít pracovat?  
  
1.  [Instalací kolekce](#BKMK_Install_the_IntelliTrace_Stand_Alone_Collector)  
  
2.  [Nastavení oprávnění pro adresáře kolekce](#ConfigurePermissionsRunningCollector)  
  
3.  [Instalace rutin prostředí IntelliTrace PowerShell pro shromažďování dat pro webové aplikace nebo aplikací služby SharePoint](#BKMK_Set_up_the_IntelliTrace_PowerShell_commandlets)  
  
4.  [Nastavení oprávnění pro adresář souboru .iTrace](#BKMK_Create_and_Configure_a_Log_File_Directory)  
  
5.  [Shromažďování dat z webové aplikace nebo aplikace SharePoint](#BKMK_Collect_Data_from_IIS_Application_Pools)  
  
     -nebo-  
  
     [Shromažďování dat ze spravované aplikace](#BKMK_Collect_Data_from_Executables)  
  
6.  [Otevřete soubor .iTrace ve Visual Studio Enterprise](#BKMK_View_IntelliTrace_Log_Files)  
  
##  <a name="BKMK_Install_the_IntelliTrace_Stand_Alone_Collector"></a>Instalací kolekce  
  
1.  Na serveru vaší aplikace vytvořte adresář kolekce, například: **C:\IntelliTraceCollector**  
  
2.  Získání kolekce z webu Microsoft Download Center nebo z instalační složky sady Visual Studio 2013 Update 3. [Kolekce IntelliTrace pro Visual Studio 2013 Update 4](https://www.microsoft.com/en-us/download/details.aspx?id=44909)::  
  
    -   **Microsoft Download Center**:  
  
        1.  Vedle **IntelliTraceCollector.exe**, zvolte **Stáhnout**.  
  
        2.  Uložit IntelliTraceCollector.exe do adresáře kolekce, například: **C:\IntelliTraceCollector**  
  
        3.  Spusťte IntelliTraceCollector.exe. To vyextrahuje IntelliTraceCollection.cab souboru.  
  
         \-nebo –  
  
    -   **Instalační složka nástroje Visual Studio**:  
  
        1.  Zkopírujte IntelliTraceCollection.cab z následující složku:  
  
             **.. 12.0\Common7\IDE\CommonExtensions\Microsoft\IntelliTrace\12.0.0 \Microsoft visual Studio**  
  
        2.  Uveďte IntelliTraceCollection.cab v adresáři kolekce, například: **C:\IntelliTraceCollector**  
  
3.  Rozbalte IntelliTraceCollection.cab:  
  
    1.  Na serveru vaší aplikace otevřete okno příkazového řádku jako správce.  
  
    2.  Vyhledejte adresář, kolekce, například: **C:\IntelliTraceCollector**  
  
    3.  Použití **rozbalte** příkazu, včetně období (**.**) na konci, chcete-li rozšířit IntelliTraceCollection.cab:  
  
         `expand  /f:* IntelliTraceCollection.cab .`  
  
        > [!NOTE]
        >  Období (**.**) zachovává podsložkám, které obsahují plány lokalizované kolekce.  
  
##  <a name="ConfigurePermissionsRunningCollector"></a>Nastavení oprávnění pro adresáře kolekce  
  
1.  Na serveru vaší aplikace otevřete okno příkazového řádku jako správce.  
  
2.  Použití Windows **icacls** příkaz poskytnout serveru úplná oprávnění správce k adresáři kolekce. Příklad:  
  
     `icacls "C:\IntelliTraceCollector" /grant "` *\<Domain\AdministratorID >*`":F`  
  
3.  Ke shromažďování dat pro webovou aplikaci nebo aplikaci služby SharePoint:  
  
    1.  Poskytněte osobě, která se spustí rutin prostředí IntelliTrace PowerShell úplná oprávnění k adresáři kolekce.  
  
         Příklad:  
  
         `icacls "C:\IntelliTraceCollector" /grant "` *\<Doména\ID_uživatele >*`":F`  
  
    2.  Zadejte fond aplikací pro webové aplikace nebo aplikace SharePoint číst a spouštět oprávnění k adresáři kolekce.  
  
         Příklad:  
  
        -   Pro webovou aplikaci v **DefaultAppPool** fondu aplikací:  
  
             `icacls "C:\IntelliTraceCollector" /grant "IIS APPPOOL\DefaultAppPool":RX`  
  
        -   Pro aplikaci služby SharePoint v **SharePoint - 80** fondu aplikací:  
  
             `icacls "C:\IntelliTraceCollector" /grant "IIS APPPOOL\SharePoint - 80":RX`  
  
##  <a name="BKMK_Set_up_the_IntelliTrace_PowerShell_commandlets"></a>Instalace rutin prostředí IntelliTrace PowerShell pro shromažďování dat pro webové aplikace nebo aplikací služby SharePoint  
  
1.  Ujistěte se, že je povolené prostředí PowerShell na serveru vaší aplikace. Na většině verze systému Windows Server, můžete přidat tuto funkci v **správce serveru** nástroj pro správu.  
  
     ![Přidání prostředí PowerShell pomocí Správce serveru](../debugger/media/intellitrace_servermanager_addpowershell.png "INTELLITRACE_ServerManager_AddPowerShell")  
  
2.  Nainstalujte rutiny Powershellu IntelliTrace.  
  
    1.  Otevřete příkazové okno prostředí PowerShell jako správce.  
  
        1.  Zvolte **spustit**, **všechny programy**, **Příslušenství**, **prostředí Windows PowerShell**.  
  
        2.  Vyberte jednu z následujících kroků:  
  
            -   Na 64bitové operační systémy, otevřete místní nabídku pro **prostředí Windows PowerShell**. Zvolte **spustit jako správce**.  
  
            -   Na 32bitové operační systémy, otevřete místní nabídku pro **prostředí Windows PowerShell (x86)**. Zvolte **spustit jako správce**.  
  
    2.  V příkazové okno prostředí PowerShell pomocí **Import-Module** příkazu naimportujte **Microsoft.VisualStudio.IntelliTrace.PowerShell.dll**.  
  
         Příklad:  
  
         `Import-Module "C:\IntelliTraceCollector\Microsoft.VisualStudio.IntelliTrace.PowerShell.dll"`  
  
##  <a name="BKMK_Create_and_Configure_a_Log_File_Directory"></a>Nastavení oprávnění pro adresář souboru .iTrace  
  
1.  Na serveru vaší aplikace vytvořte adresář souboru .iTrace, například: **C:\IntelliTraceLogFiles**  
  
    > [!NOTE]
    >  -   Abyste se vyhnuli zpomalení vaší aplikace, vyberte umístění na místním disku vysokorychlostní, který není velmi aktivní.  
    > -   Soubory .iTrace a collector soubory můžete umístit na stejném místě. Ale pokud máte webovou aplikaci nebo aplikaci služby SharePoint, zajistěte, aby byl tento místní mimo adresář, který je hostitelem aplikace.  
  
    > [!IMPORTANT]
    >  -   Adresář souboru .iTrace omezte pouze na tyto identity, které musíte spolupracovat s kolekce. Soubor .iTrace můžou obsahovat citlivé informace, třeba dat z uživatelů, databází, jiné umístění zdrojových souborů a připojovací řetězce, protože IntelliTrace můžete zaznamenat všechna data, která předá do parametrů metody nebo jako návratové hodnoty.  
    > -   Ujistěte se, že ty, kteří můžete otevřít soubory .iTrace jsou oprávněni zobrazit citlivá data. Při sdílení soubory .iTrace buďte opatrní. Pokud ostatní uživatelé musí mít přístup, zkopírujte soubory do zabezpečeného umístění sdílené.  
  
2.  Pro webovou aplikaci nebo aplikaci služby SharePoint zadejte svůj fond aplikací úplná oprávnění k adresáři souboru .iTrace. Můžete použít Windows **icacls** příkaz nebo pomocí Průzkumníka Windows (nebo Průzkumníka souborů).  
  
     Příklad:  
  
    -   Nastavit oprávnění s Windows **icacls** příkaz:  
  
        -   Pro webovou aplikaci v **DefaultAppPool** fondu aplikací:  
  
             `icacls "C:\IntelliTraceLogFiles" /grant "IIS APPPOOL\DefaultAppPool":F`  
  
        -   Pro aplikaci služby SharePoint v **SharePoint - 80** fondu aplikací:  
  
             `icacls "C:\IntelliTraceLogFiles" /grant "IIS APPPOOL\SharePoint - 80":F`  
  
         -nebo-  
  
    -   Nastavení oprávnění pro Průzkumníka Windows (nebo v Průzkumníku souborů):  
  
        1.  Otevřete **vlastnosti** pro adresář .iTrace souboru.  
  
        2.  Na **zabezpečení** , zvolte **upravit**, **přidat**.  
  
        3.  Zajistěte, aby **předdefinované objekty zabezpečení** se zobrazí v **vyberte tento typ objektu** pole. Pokud se má existuje, volbu **typy objektů** ho přidejte.  
  
        4.  Ujistěte se, že se zobrazí v místním počítači **z tohoto umístění** pole. Pokud se má existuje, volbu **umístění** ho změnit.  
  
        5.  V **zadejte názvy objektů k výběru** pole, přidat fond aplikací pro webovou aplikaci nebo aplikaci služby SharePoint.  
  
        6.  Zvolte **Kontrola názvů** přeložit název. Zvolte **OK**.  
  
        7.  Ověřte, zda fond aplikací má **úplné řízení**.  
  
##  <a name="BKMK_Collect_Data_from_IIS_Application_Pools"></a>Shromažďování dat z webové aplikace nebo aplikace SharePoint  
  
1.  Pokud chcete spustit shromažďování dat, otevřete příkazové okno prostředí PowerShell jako správce, a poté spusťte tento příkaz:  
  
     `Start-IntelliTraceCollection``"`  *\<ApplicationPool >* `"`  *\<PathToCollectionPlan >*  *\< FullPathToITraceFileDirectory >*  
  
    > [!IMPORTANT]
    >  Když spustíte tento příkaz, zadejte **Y** potvrďte, že chcete spustit shromažďování dat.  
  
     Například pro shromažďování dat z aplikace služby SharePoint v **SharePoint - 80** fondu aplikací:  
  
     `Start-IntelliTraceCollection "SharePoint - 80" "C:\IntelliTraceCollector\collection_plan.ASP.NET.default.xml" "C:\IntelliTraceLogFiles"`  
  
    |||  
    |-|-|  
    |*ApplicationPool*|Název fondu aplikací, kde vaše aplikace běží|  
    |*PathToCollectionPlan*|Cesta k plán kolekce, soubor .xml, který konfiguruje nastavení pro kolekci.<br /><br /> Můžete zadat plán, který se dodává s kolekce. Následujících plánů pracovních pro webové aplikace a aplikací služby SharePoint:<br /><br /> -collection_plan.ASP.NET.default.xml<br />     Shromažďuje jenom události IntelliTrace a události služby SharePoint, včetně výjimek, volání databáze a požadavky webový server.<br />-collection_plan.ASP.NET.trace.xml<br />     Volání funkcí shromažďuje a všechna data v collection_plan.ASP.NET.default.xml. Tento plán je vhodný pro podrobné analýzy, ale může zpomalit víc než collection_plan.ASP.NET.default.xml aplikace.<br /><br /> Abyste se vyhnuli zpomalení vaší aplikace, přizpůsobit tyto plány nebo vytvořit vlastní plán. Pro zabezpečení uveďte všechny vlastní plány ve stejném zabezpečené umístění jako soubory kolekce. V tématu [vytváření a přizpůsobení plánů kolekce IntelliTrace](http://go.microsoft.com/fwlink/?LinkId=227871) a [získání nejvíce dat bez zpomalení mé aplikace?](#Minimizing) **Poznámka:** ve výchozím nastavení je maximální velikost souboru .iTrace 100 MB. Pokud soubor .iTrace dosáhne tento limit, odstraní kolekce nejdřívější položky souboru k uvolnění místa pro položky novější. Chcete-li tento limit změnit, upravte plán kolekce `MaximumLogFileSize` atribut. <br /><br /> *Kde najdu lokalizované verze tyto plány kolekce?*<br /><br /> Lokalizované plány můžete najít v podsložkách kolekce.|  
    |*FullPathToITraceFileDirectory*|Úplná cesta k adresáři souboru .iTrace. **Poznámka k zabezpečení:** zadat úplnou cestu, nejedná se o relativní cestu.|  
  
     Kolekce připojí k fondu aplikací a spustí shromažďování dat.  
  
     *Můžete otevřít soubor .iTrace nyní?* Ne, je soubor uzamčený během shromažďování dat.  
  
2.  Reprodukujte problém.  
  
3.  K pořízení snímku souboru .iTrace, použijte následující syntaxi:  
  
     `Checkpoint-IntelliTraceCollection``"`  *\<ApplicationPool >*`"`  
  
4.  Chcete-li zkontrolovat stav kolekce, použijte následující syntaxi:  
  
     `Get-IntelliTraceCollectionStatus`  
  
5.  Chcete-li zastavit shromažďování dat, použijte následující syntaxi:  
  
     `Stop-IntelliTraceCollection``"`  *\<ApplicationPool >*`"`  
  
    > [!IMPORTANT]
    >  Když spustíte tento příkaz, zadejte **Y** potvrďte, že chcete zastavit shromažďování dat. Kolekce, jinak může pokračovat ve shromažďování dat, iTrace soubor zůstane uzamčení nebo soubor nemusí obsahovat potřebná data.  
  
6.  [Otevřete soubor .iTrace ve Visual Studio Enterprise](#BKMK_View_IntelliTrace_Log_Files)  
  
##  <a name="BKMK_Collect_Data_from_Executables"></a>Shromažďování dat ze spravované aplikace  
  
1.  Spusťte aplikaci a shromažďování dat ve stejnou dobu, použijte následující syntaxi:  
  
     *\<FullPathToIntelliTraceCollectorExecutable >* `\IntelliTraceSC.exe launch /cp:`  *\<PathToCollectionPlan >* `/f:`  *\< FullPathToITraceFileDirectoryAndFileName >*  *\<PathToAppExecutableFileAndFileName >*  
  
     Například ke shromažďování dat z aplikace s názvem **Moje aplikace**:  
  
     `C:IntelliTraceCollectorIntelliTraceSC.exe launch /cp:"C:IntelliTraceCollectorcollection_plan.ASP.NET.default.xml" /f:"C:IntelliTraceLogFilesMyApp.itrace" "C:MyAppMyApp.exe"`  
  
    |||  
    |-|-|  
    |*FullPathToIntelliTraceCollectorExecutable*|Úplná cesta k spustitelný soubor, kolekce IntelliTraceSC.exe|  
    |*PathToCollectionPlan*|Cesta k plán kolekce, soubor .xml, který konfiguruje nastavení pro kolekci.<br /><br /> Můžete zadat plán, který se dodává s kolekce. Pro spravované aplikace fungují následujících plánů:<br /><br /> -collection_plan.ASP.NET.default.xml<br />     Shromažďuje IntelliTrace pouze události, včetně výjimek, volání databáze a požadavky webový server.<br />-collection_plan.ASP.NET.trace.xml<br />     Volání funkcí shromažďuje a všechna data v collection_plan.ASP.NET.default.xml. Tento plán je vhodný pro podrobné analýzy, ale může zpomalit víc než collection_plan.ASP.NET.default.xml aplikace.<br /><br /> Abyste se vyhnuli zpomalení vaší aplikace, přizpůsobit tyto plány nebo vytvořit vlastní plán. Pro zabezpečení uveďte všechny vlastní plány ve stejném zabezpečené umístění jako soubory kolekce. V tématu [vytváření a přizpůsobení plánů kolekce IntelliTrace](http://go.microsoft.com/fwlink/?LinkId=227871) a [získání nejvíce dat bez zpomalení mé aplikace?](#Minimizing) **Poznámka:** ve výchozím nastavení je maximální velikost souboru .iTrace 100 MB. Pokud soubor .iTrace dosáhne tento limit, odstraní kolekce nejdřívější položky souboru k uvolnění místa pro položky novější. Chcete-li tento limit změnit, upravte plán kolekce `MaximumLogFileSize` atribut. <br /><br /> *Kde najdu lokalizované verze tyto plány kolekce?*<br /><br /> Lokalizované plány můžete najít v podsložkách kolekce.|  
    |*FullPathToITraceFileDirectoryAndFileName*|Úplná cesta k adresáři souboru .iTrace a název souboru .iTrace **.itrace** rozšíření. **Poznámka k zabezpečení:** zadat úplnou cestu, nejedná se o relativní cestu.|  
    |*PathToAppExecutableFileAndFileName*|Název a cesta k souboru spravované aplikace|  
  
2.  Zastavte shromažďování dat ukončení aplikace.  
  
3.  [Otevřete soubor .iTrace ve Visual Studio Enterprise](#BKMK_View_IntelliTrace_Log_Files)  
  
##  <a name="BKMK_View_IntelliTrace_Log_Files"></a>Otevřete soubor .iTrace ve Visual Studio Enterprise  
  
> [!NOTE]
>  Ladění pomocí technologie IntelliTrace a krok prostřednictvím kódu, musí mít odpovídající zdrojové soubory a soubory symbolů. V tématu [Diagnostika problémů po nasazení](../debugger/diagnose-problems-after-deployment.md).  
  
1.  Přesuňte soubor .iTrace nebo ho zkopírujte do počítače s Visual Studio Enterprise (ale ne Professional nebo komunity edice).  
  
2.  Poklikejte na soubor .iTrace mimo Visual Studio, nebo otevřít soubor z v sadě Visual Studio.  
  
     Visual Studio zobrazí **IntelliTrace Souhrn** stránky. Ve většině částí, můžete zkontrolujte události nebo jiných položek, vyberte položku a začít ladění pomocí technologie IntelliTrace v místě, kde a kdy události došlo. V tématu [pomocí uložit dat technologie IntelliTrace](../debugger/using-saved-intellitrace-data.md).  
  
    > [!NOTE]
    >  Ladění pomocí technologie IntelliTrace a krok prostřednictvím kódu, musí mít odpovídající zdrojové soubory a soubory na vývojovém počítači symbolů. V tématu [Diagnostika problémů po nasazení](../debugger/diagnose-problems-after-deployment.md).  
  
##  <a name="Minimizing"></a>Jak získat většinu dat bez zpomalení mé aplikace?  
 IntelliTrace může shromažďovat velké množství dat, takže dopad na výkon vaší aplikace závisí na data, která shromažďuje IntelliTrace a druh kód, který analyzuje. V tématu [optimalizace shromažďování snímků IntelliTrace na provozních serverech](http://go.microsoft.com/fwlink/?LinkId=255233).  
  
 Tady jsou některé způsoby, jak získat většinu dat bez zpomalení aplikace:  
  
-   Kolekce spusťte pouze v případě, že si myslíte, že došlo k potížím, nebo když lze problém reprodukovat.  
  
     Spustit shromažďování, reprodukujte problém a poté zastavte kolekce. Otevřete soubor .iTrace ve Visual Studio Enterprise a kontrolovat data. V tématu [otevřete soubor .iTrace ve Visual Studio Enterprise](#BKMK_View_IntelliTrace_Log_Files).  
  
-   Pro webové aplikace a aplikací služby SharePoint kolekce zaznamenává data pro každou aplikaci, která sdílí zadaný fond aplikací. Může dojít ke zpomalení jakékoli aplikaci, která sdílí stejný fond aplikací, i když můžete zadat pouze moduly pro jednoduché aplikace v plánu kolekce.  
  
     Abyste zabránili kolekce zpomalením z jiných aplikací, hostitel každou aplikaci ve vlastním fondu aplikací.  
  
-   Zkontrolujte v plánu kolekce, pro kterou IntelliTrace shromažďuje data události. Upravte plán kolekce zakázat události, které nejsou relevantní, nebo nemáte vás zajímají.  
  
     Chcete-li zakázat událost, nastavte `enabled` atribut pro `<DiagnosticEventSpecification>` elementu, který chcete `false`:  
  
     `<DiagnosticEventSpecification enabled="false">`  
  
     Pokud `enabled` atribut neexistuje, je událost povolena.  
  
     *Jak to zlepšit výkon?*  
  
    -   Zakázáním události, které nejsou relevantní pro aplikaci můžete zkrátit dobu spuštění. Například zakážete události pracovního postupu systému Windows pro aplikace, které nepoužívají Windows Workflow.  
  
    -   Můžete zlepšit výkon při spuštění a prostředí runtime zakázáním registru události pro aplikace, které přístup do registru, ale nezobrazovat problémy s nastavením registru.  
  
-   Zkontrolujte moduly v plánu kolekce, pro kterou IntelliTrace shromažďuje data. Upravte plán kolekce zahrnout pouze moduly, které vás zajímají:  
  
    1.  Otevřete plán kolekcí. Najít `<ModuleList>` elementu.  
  
    2.  V `<ModuleList>`, nastavte `isExclusionList` atribut `false`.  
  
    3.  Použití `<Name>` elementu, který chcete určit každý modul s jedním z následujících akcí: název souboru, řetězcovou hodnotu zahrnout libovolný modul, jejichž název obsahuje tento řetězec nebo veřejný klíč.  
  
     Například ke shromažďování dat z právě hlavní modulu Web společnosti Fabrikam Fiber webové aplikace, můžete vytvořte seznam podobné následujícímu:  
  
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
  
     *Jak to zlepšit výkon?*  
  
     Tím se snižuje množství informací o volání metody a další instrumentace data, která shromažďuje IntelliTrace při spuštění a spuštění aplikace. Tato data vám umožní:  
  
    -   Po shromáždění dat krok prostřednictvím kódu.  
  
    -   Zkontrolujte hodnoty předaný a vrácená z volání funkce.  
  
     *Proč ne vyloučit moduly místo?*  
  
     Ve výchozím nastavení, plány kolekce vyloučit moduly nastavením `isExclusionList` atribut `true`. Ale s výjimkou moduly může stále dojít shromažďování dat z modulů, které nesplňují kritéria v seznamu a nemusí zajímají, jako je například modulů třetích stran nebo open source.  
  
-   *Je k dispozici žádná data, která není shromažďování IntelliTrace?*  
  
     Ano, abyste snížili vliv na výkon, omezuje IntelliTrace shromažďování dat na hodnoty primitivní datové typy předaný a vrácených z metod a hodnoty primitivní datové typy polí na nejvyšší úrovně objekty předaný a byla vrácena z metod.  
  
     Předpokládejme například, že máte `AlterEmployee` podpis metody, který přijímá celé `id` a `Employee` objekt `oldemployee`:  
  
     `public Employee AlterEmployee(int id, Employee oldemployee)`  
  
     `Employee` Typ má následující atributy: `Id`, `Name`, a `HomeAddress`. Přidružení vztah mezi `Employee` a `Address` typu.  
  
     ![Vztah mezi zaměstnanci a adresu](../debugger/media/employeeaddressrelationship.png "EmployeeAddressRelationship")  
  
     Kolekce zaznamenává hodnoty pro `id`, `Employee.Id`, `Employee.Name` a `Employee` objekt vrácený `AlterEmployee` metoda. Však nepodporuje kolekce zaznamenejte informace o `Address` objektu, než bez ohledu na jeho, jestli byla null. Kolekce nemá také zaznamenat data o místní proměnné v `AlterEmployee` metoda Pokud jiné metody použít tyto místní proměnné jako parametry v tomto okamžiku se zaznamenávají jako parametry metody.  
  
##  <a name="WhereElse"></a>Jinak kde může získat dat technologie IntelliTrace?  
  
-   Ze služby IntelliTrace ladicí relace ve Visual Studio Enterprise, najdete v části [funkce IntelliTrace](../debugger/intellitrace-features.md).  
  
-   Z relace testování v Microsoft Test Manager, najdete na stránce [postupy: shromáždění dat technologie IntelliTrace pro pomůže ladění složitých problémů](http://msdn.microsoft.com/Library/02b6716f-569e-4961-938a-e790a0c74b5c).  
  
## <a name="where-can-i-get-more-information"></a>Kde lze získat další informace?  
 [Pomocí uložených dat technologie IntelliTrace](../debugger/using-saved-intellitrace-data.md)  
  
 [IntelliTrace](../debugger/intellitrace.md)  
  
### <a name="blogs"></a>Blogy  
 [Pomocí Kolektoru IntelliTrace samostatné vzdáleně](http://go.microsoft.com/fwlink/?LinkId=262277)  
  
 [Vytváření a přizpůsobení plány kolekce IntelliTrace](http://go.microsoft.com/fwlink/?LinkId=227871)  
  
 [Optimalizace shromažďování snímků IntelliTrace na provozních serverech](http://go.microsoft.com/fwlink/?LinkId=255233)  
  
 [Visual Studio ALM a TFS Blog](http://go.microsoft.com/fwlink/?LinkID=201340)  
  
### <a name="forums"></a>Diskuzní fóra  
 [Ladicí program Visual Studio](http://go.microsoft.com/fwlink/?LinkId=262263)  
  
### <a name="videos"></a>Videa  
 [Channel 9 video: shromažďování a analýzy dat technologie IntelliTrace](http://go.microsoft.com/fwlink/?LinkID=251851)
