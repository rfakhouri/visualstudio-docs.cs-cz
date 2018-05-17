---
title: Instalace a použití sady Visual Studio a služby Azure za serverem brány firewall nebo proxy server | Microsoft Docs
description: Zkontrolujte domény adresy URL, porty a protokoly, které může chcete seznamu povolených IP adres nebo otevřít, pokud vaše organizace používá Brána firewall nebo proxy server
ms.custom: ''
ms.date: 02/12/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 304c31a9cfd389bb3a5af6b1a8191f41d881165b
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2018
---
# <a name="install-and-use-visual-studio-and-azure-services-behind-a-firewall-or-proxy-server"></a>Instalace a použití sady Visual Studio a služby Azure za serverem brány firewall nebo proxy server

Pokud vaše organizace používá bezpečnostní opatření, jako je například Brána firewall nebo proxy server, pak jsou domény adresy URL, které můžete chtít "povolených" a porty a protokoly, které můžete chtít otevřít tak, aby měli dosažení co nejlepších výsledků při instalaci a použití samostatného Visual dio a služby Azure.

* **[Instalaci sady Visual Studio](#install-visual-studio)**: tyto tabulky obsahují domény adresy URL do seznamu povolených IP adres, aby měli přístup ke všem součásti a úlohy, které chcete.

* **[Pomocí sady Visual Studio a služby Azure](#use-visual-studio-and-azure-services)**: Tato tabulka obsahuje domény adresy URL do seznamu povolených IP adres a portů a protokolů otevřete tak, aby měli přístup ke všem funkce a služby, které chcete.

## <a name="install-visual-studio"></a>Instalaci sady Visual Studio

### <a name="urls-to-whitelist"></a>Adresy URL do seznamu povolených IP adres

Vzhledem k tomu, že instalační program Visual Studio stáhne soubory z různých domén a jejich stahování serverů, tady jsou uvedené adresy URL domény, které můžete chtít povolených jako důvěryhodné v uživatelském rozhraní nebo ve skriptech nasazení.

#### <a name="microsoft-domains"></a>Microsoft domains

| Domény | Účel |
| ------ | ------- |
| go.microsoft.com | Překlad adresy URL instalace |
| aka.ms | Překlad adresy URL instalace |
| download.visualstudio.microsoft.com | Nastavení umístění stahování balíčků |
| download.microsoft.com | Nastavení umístění stahování balíčků |
| download.visualstudio.com | Nastavení umístění stahování balíčků |
| dl.xamarin.com | Nastavení umístění stahování balíčků |
| visualstudiogallery.msdn.microsoft.com | Umístění souboru ke stažení rozšíření Visual Studia |
| www.visualstudio.com | Umístění dokumentace |
| docs.microsoft.com | Umístění dokumentace |
| msdn.microsoft.com | Umístění dokumentace |
| www.microsoft.com | Umístění dokumentace |
| *.windows.net | Přihlášení |
| *.microsoftonline.com | Přihlášení |
| *.live.com | Přihlášení |
|  |  | |

#### <a name="non-microsoft-domains"></a>Domény od jiných výrobců

| Domény | Nainstaluje tyto úlohy |
| ------ | ------- |
| archive.apache.org |  Mobilní vývoj v jazyce JavaScript (Cordova) |
| cocos2d-x.org | Vývoj her s jazykem C++ (Kokosové) |
| download.epicgames.com | Vývoj her s jazykem C++ (Unreal Engine) |
| download.oracle.com | Mobilní vývoj v jazyce JavaScript (Java SDK) <br /><br />Mobilní vývoj pomocí rozhraní .NET (Java SDK) |
| download.unity3d.com | Vývoj her s Unity (Unity) |
| netstorage.unity3d.com | Vývoj her s Unity (Unity) |
| dl.google.com | Mobilní vývoj v jazyce JavaScript (Android SDK a NDK, emulátor) <br /><br />Mobilní vývoj pomocí rozhraní .NET (Android SDK a NDK, emulátor) |
| www.incredibuild.com | Vývoj her s jazykem C++ (IncrediBuild) |
| incredibuildvs2017i.azureedge.net | Vývoj her s jazykem C++ (IncrediBuild) |
| www.python.org | Vývoj Python (Python) <br /><br />Vědecké zpracování dat a analytických aplikací (Python) |
|  |  | |

## <a name="use-visual-studio-and-azure-services"></a>Pomocí aplikace Visual Studio a službami Azure

### <a name="urls-to-whitelist-and-ports-and-protocols-to-open"></a>Adresy URL do seznamu povolených IP adres a portů a protokolů otevřete

Pokud chcete mít jistotu, že máte přístup k vše potřebné při použití sady Visual Studio nebo služby Azure za serverem brány firewall nebo proxy, tady jsou uvedené adresy URL, měli byste seznamu povolených IP adres a porty a protokoly, které chcete otevřít.

| Služba nebo scénáře | Koncový bod služby DNS | Protokol | port | Popis |
| --- | --- | --- | --- | --- |
| Adresa URL<br>rozlišení | go.microsoft.com<br><br>aka.ms | | |Slouží ke zkrácení adresu URL, která potom vyřešte do delší adresy URL
| Úvodní stránka | vsstartpage.blob.core.windows.net | | 443| Slouží k zobrazení zprávy vývojáře zobrazený na stránce start v sadě Visual Studio |
| Cílem<br> oznámení <br>Služba | targetednotifications.azurewebsites.net <br><br>www.research.net | | 80<br><br>443| Použito pro filtrování seznamu pro globální oznámení do seznamu, který se vztahuje pouze na konkrétní typy počítačů nebo využití scénáře |
| Rozšíření <br>Kontrola aktualizací | visualstudiogallery.msdn.microsoft.com<br><br>&#42;.windows.net <br>&#42;.microsoftonline.com <br>&#42;.live.com  | | 443 | Použitý k poskytnutí oznámení, když má nainstalovaná rozšíření k dispozici aktualizace. <br><br> Použít jako umístění přihlášení|
| Projekt AI <br>Integrace | az861674.vo.msecnd.net  | | 443<br> | Slouží ke konfiguraci nových projektů se mají posílat data o využití účtu registrované Application Insights |
| Kód přehledu | codelensprodscus1su0.app.<br>codelens.visualstudio.com | |443 | Používá k poskytování informací v editoru o poslední aktualizace souboru, časové ose změny, pracovní položky, které jsou přidružené změny, autorů a další|
|experimentální <br>povolení funkce  | visualstudio-devdiv-c2s.msedge.net | |80 | Použít k aktivaci experimentální nové funkce nebo funkce změny |
| Identity "badge" <br>(uživatelské jméno a miniatury)<br>and <br>Nastavení roamingu | app.vssps.visualstudio.com <br><br>app.vsspsext.visualstudio.com<br><br>app.vssps.visualstudio.com<br><br> ns-sb2-prod-ch1-002.cloudapp.net <br><br>az700632.vo.msecnd.net  | |443 | Zobrazuje název a miniaturu uživatele v prostředí IDE <br><br> Používá k zajištění toho, že změny nastavení přesouvat z jednoho počítače do druhého |
| Nastavení vzdáleného přístupu | az700632.vo.msecnd.net | | 443| Umožňuje vypnout rozšíření, které způsobují problémy v sadě Visual Studio   |
| Nástroje systému Windows | developer.microsoft.com <br><br>dev.windows.com  <br><br>appdev.microsoft.com |protokol HTTPS |443 | Používá se při scénářích úložiště aplikace Windows  |
| Schématu JSON <br>Zjišťování <br><br>Schématu JSON <br>Definice<br><br>Schématu JSON <br>Podpora pro <br>Prostředky Azure| json.schemastore.org <br>schemastoreorg.azurewebsites.net<br><br>json-schema.org<br><br>schema.management.azure.com| http<br>protokol HTTPS<br><br>http<br><br>protokol HTTPS |80<br>443 <br><br> 443<br><br>443 | Umožňuje vyhledat a stáhnout schémata JSON, které může uživatel použít při úpravě dokumentů JSON <br><br>Použít k získání schématu meta ověření pro formát JSON<br><br>Umožňuje získat aktuální schéma pro nasazení šablony Azure Resource Manager|
| Balíčku NPM <br>zjištění  |Skimdb.npmjs.com <br><br>Registry.npmjs.org <br><br>Api.npms.io  | protokol HTTPS<br><br>HTTP/s<br><br>protokol HTTPS | 443<br><br>80/443<br><br>443| Je požadována pro vyhledávání balíčků NPM a použitý k instalaci balíčku klientský skript v webové projekty |
|Bower balíčku<br> ikony<br><br>Bower balíčku <br>search  |Bower.IO <br><br>bowercache.azurewebsites.net <br>go.microsoft.com <br>Registry.bower.IO | http<br><br>protokol HTTPS<br>http<br>protokol HTTPS|80<br><br>443<br>80<br>443 |Poskytuje výchozí ikonu balíčku bower  <br><br>Umožňuje vyhledat Bower balíčky |
|NuGet<br><br>Balíček NuGet<br> zjištění | API.nuget.org <br>www.nuget.org <br>Nuget.org<br><br>crl3.digicert.com <br>crl4.digicert.com <br>ocsp.digicert.com <br>cacerts.digicert.com  | protokol HTTPS<br><br>HTTP/s |443<br><br>80/443<br> |Používají k ověření podepsané balíčky NuGet.<br><br>Vyžaduje se pro hledání balíčků NuGet a verze |
|Informace o úložišti GitHub  |api.github.com  |protokol HTTPS | 443| Vyžaduje se pro získání dalších informací o balíčcích, bower |
| Webové Linters|Eslint.org<br><br>www.Bing.com <br><br>www.coffeelint.org  | http|80 | |
| Cookiecutter<br>Průzkumník šablony<br>zjištění <br><br>Cookiecutter <br>Průzkumník projektu<br> Vytvoření | api.github.com <br>RAW.githubusercontent.com <br>go.microsoft.com<br><br>pypi.org <br> pypi.python.org  | protokol HTTPS | 443<br> | Používá ke zjišťování online šablony z našich Doporučený kanál a úložišť github <br><br>Použít k vytváření projektů z cookiecutter šablonu, která vyžaduje jednorázovou instalaci na vyžádání balíček Python cookiecutter z indexu balíčků Pythonu (úložiště PyPI)|
| Balíček Python <br>zjištění<br><br>Balíček Python <br>management<br><br>Python <br>Nový projekt <br>šablony| pypi.org<br> <br>pypi.python.org <br>bootstrap.pypa.io<br><br>go.microsoft.com| protokol HTTPS| 443| Umožňuje vyhledat pip balíčky<br><br>Použitý k instalaci pip automaticky, pokud není nalezena <br><br> Umožňuje vytvořit <br><br>Slouží k rozpoznávání, že následující Python šablony v dialogovém okně Nový projekt na adresy URL cookiecutter šablony projektu:<br> -Třídění projektu<br>– Clustering projektu <br> -Regression projektu <br> -PyGame pomocí PyKinect <br> -Pyvot projektu |
| Office web <br>doplněk <br> Manifest <br>Ověření <br>Služba | verificationservice.osi.office.net | protokol HTTPS | 443 | Slouží k ověření manifesty pro doplňky webové sady Office |
| SharePoint a <br>Doplňky sady Office | sharepoint.com | protokol HTTPS | 443 | Použít při publikování a testování služby SharePoint a doplňky Office ke službě SharePoint Online |
| Správce pracovních postupů <br>Testování služby<br> Hostitel |  | http | 12292 | Pravidlo brány firewall, který je automaticky vytvořen pro testování doplňky s pracovními postupy služby SharePoint |
| Automaticky shromažďovat <br>spolehlivost statistiky <br>a další <br>Zkušeností zákazníků <br>Programů zlepšování (uživatelů CEIP)<br> pro Azure SDK a <br>nástroje SQL <br><br> | vortex.data.microsoft.com<br> <br>dc.services.visualstudio.com |protokol HTTPS | 443| Používá k odeslání spolehlivost statistiky (Chyba/zablokování data) od uživatele společnosti Microsoft. Skutečné Chyba/zablokování výpisy budou odeslány stále, pokud je povoleno zasílání zpráv o chybách systému Windows; pouze statistické informace budou potlačeny; <br>Použít na nich anonymní vzorce pro rozšíření Azure Tools SDK pro Visual Studio a vzorce používání SQL nástrojů pro Visual Studio |
| Visual Studio <br> Zkušeností zákazníků <br>Programu zlepšování softwaru a (uživatelů CEIP) <br><br>PerfWatson.exe | vortex.data.microsoft.com<br>dc.services.visualstudio.com<br>visualstudio-devdiv-c2s.msedge.net<br>az667904.vo.msecnd.net <br>scus-breeziest-in.cloudapp.net<br> | protokol HTTPS| 443 | Používá ke shromažďování anonymních vzorce a protokoly chyb <br><br>Používá ke sledování problémů zablokování uživatelského rozhraní|
| Vytvoření a<br>Správa <br>Prostředky Azure | management.azure.com <br>management.core.windows.net   | protokol HTTPS | 443 | Použít pro vytváření webů Azure nebo další prostředky pro podporu publikování webových aplikací, Azure Functions nebo webové úlohy |
| Publikování aktualizované webu nástrojů <br>kontroly a rozšíření <br>Doporučení  | marketplace.visualstudio.com  <br> visualstudiogallery.msdn.microsoft.com  | protokol HTTPS | 443 | Použít pro kontrolu pro dostupnost aktualizovat publikování nástrojů. Pokud je zakázaná, nemusí být zobrazeny potenciální doporučená rozšíření pro publikování na webu |
| Aktualizovaný prostředek Azure <br>Informace o vytvoření koncového bodu  | *.blob.core.windows.net | protokol HTTPS | 443 | Použít k aktualizaci koncových bodů použitých pro vytváření prostředků Azure pro určité služby Azure. Pokud zakázané, poslední stáhnout nebo součástí koncovým bodem, který se místo toho používají umístění |
| Vzdálené ladění a <br>Vzdálená profilace z <br>Weby Azure | &#42;.cloudapp.net <br> &#42;.azurewebsites.net | | 4022 | Použít pro připojení vzdáleného ladicího programu na weby Azure. Pokud je zakázaná, nebude fungovat připojení vzdáleného ladicího programu na weby Azure |
| Služby Active Directory <br>Graf | graph.windows.net | protokol HTTPS | 443 | Umožňuje zřídit nové aplikace Azure Active Directory. Také používány poskytovateli připojené služby Office 365 MSGraph- |
| Azure Functions <br>Aktualizace rozhraní příkazového řádku <br>Kontrola | functionscdn.azureedge.net | protokol HTTPS | 443 | Použít pro kontrolu pro aktualizované verze rozhraní příkazového řádku Azure funkce. Pokud zakázané, uložené v mezipaměti kopii (nebo kopírování provádí součástí Azure Functions) z rozhraní příkazového řádku se použije místo |
| Cordova | npmjs.org<br>gradle.org | HTTP/s | 80/443 | Protokol HTTP se používá pro Gradle stáhne během vytváření sestavení; Protokol HTTPS se používá pro zahrnutí do projektů moduly plug-in Cordova|
| Průzkumník cloudu | 1. &#60;clusterendpoint&#62; <br>Service Fabric <br>2. &#60;koncový bod správy&#62;<br>Obecné cloudové Exp <br>3. &#60;graf koncový bod&#62;<br>Obecné cloudové Exp<br>4. &#60;koncový bod účtu úložiště&#62;<br>Uzlů úložiště <br>5. &#60;portál azure adresy URL&#62;<br>Obecné cloudové Exp <br>6. &#60;klíče trezoru koncové body&#62; <br>Virtuální počítač uzlů Azure Resource Manager<br>7. &#60;PublicIPAddressOfCluster&#62;<br>Služba Fabric vzdálené ladění a trasování ETW |   <br>1. protokolu https<br>2. protokolu https<br>3. protokolu https<br>4. protokolu https<br>5. protokol https<br>6. protokol https<br>7: tcp| 1. 19080<br>2. 443 <br>3. 443 <br>4. 443 <br>5. 443 <br>6. 443 <br>7. dynamické   | 1. Příklad: test12.eastus.cloudapp.com<br>2. Načte odběry a načte/spravuje prostředky Azure<br>3. Načte předplatných Azure zásobníku<br>4. Spravuje prostředky úložiště (Příklad: mystorageaccount.blob.core.windows.net)<br>5. "Otevřít na portálu" možnost místní nabídky (otevře prostředku na portálu Azure)<br>6. Vytvoří a použije trezorů klíčů pro ladění virtuálních počítačů (Příklad: myvault.vault.azure.net) <br><br>7. Dynamicky přiděluje blok portů na základě počtu uzlů v clusteru a k dispozici porty. <br><br>Blok port se pokusí získat třikrát počet uzlů s minimálně 10 portů.<br><br>Pro Streaming trasování je proveden pokus o získání portu bloku z 810. Pokud žádné z tohoto bloku port se už používá, je proveden pokus o získání další blok, a tak dále. (Nástroj pro vyrovnávání zatížení je prázdný, potom s největší pravděpodobností používají porty z 810) <br><br>Pro ladění, podobně jako čtyři sady bloků porty jsou vyhrazené: <br>-connectorPort: 30398, <br>-forwarderPort: 31398, <br>-forwarderPortx86: 31399,<br>-fileUploadPort: 32398<br>|
| Cloudové služby | 1. PROTOKOLU RDP<br><br>2. core.windows.net <br><br>3. management.azure.com<br> management.core.windows.net <br><br>4. &#42;.blob.core.windows.net <br>&#42;.queue.core.windows.net<br>&#42;.table.core.windows.net <br><br>5. portal.azure.com <br><br>6. &#60;uživatele Cloudová služba&#62;. cloudapp.net <br> &#60;user's VM&#62;.&#60;region&#62;.azure.com | 1. rdp <br><br> 2. protokolu https <br><br> 3. protokolu https <br><br> 4. protokolu https <br><br> 5. protokol https <br><br>6. tcp | 1. 3389 <br><br> 2. 443 <br><br> 3. 443 <br><br>4. 443 <br><br>5. 443 <br><br> 6.) 30398 <br> 6. b) 30400 <br> 6. c) 31398 <br> 6. d) 31400 <br> 6. e) 32398 <br> 6. f) 32400 | 1.  Vzdálená plocha do cloudové služby virtuálních počítačů <br><br> 2.  Součástí účtu úložiště diagnostiky privátní konfigurace <br><br> 3.  Portál Azure <br><br> 4. Průzkumník serveru - úložiště Azure &#42; je zákazník s názvem účtu úložiště  <br><br> 5.  Odkazy na otevřete portál &#47; stažení certifikátu předplatného &#47; soubor nastavení publikování <br><br>6.) konektor místní port pro vzdálené ladění pro cloudové služby a virtuálních počítačů<br> 6. b) konektor veřejný port pro vzdálené ladění pro cloudové služby a virtuálních počítačů <br> 6. c) předávání místní port pro vzdálené ladění pro cloudové služby a virtuálních počítačů <br> 6. d) předávání veřejný port pro vzdálené ladění pro cloudové služby a virtuálních počítačů  <br> 6. e) souboru osoba místní port pro vzdálené ladění pro cloudové služby a virtuálních počítačů <br> 6. f) souboru osoba veřejný port pro vzdálené ladění pro cloudové služby a virtuálních počítačů |
| Service Fabric | 1. <br>ocs.Microsoft.com<br>aka.ms <br>go.microsoft.com <br><br>2. <br>vssftools.blob.core.windows.net <br>Vault.azure.com <br>Portal.azure.com <br><br> 3. &#42; vault.azure.net<br><br> 4. <br>app.vsaex.visualstudio.com<br>&#42; .vsspsext.visualstudio.com<br>clouds.vsrm.visualstudio.com <br>clouds.visualstudio.com<br>app.vssps.visualstudio.com <br>&#42; .visualstudio.com | protokol HTTPS | 443 | 1. Dokumentace <br><br> 2. Vytvoření funkce clusteru <br><br>3. &#42; Je název Azure trezoru klíčů (Příklad:-test11220180112110108.vault.azure.net  <br><br>  4. &#42; Je dynamický (Příklad: vsspsextprodch1su1.vsspsext.visualstudio.com) |
| Snímek <br>Ladicí program | 1. go.microsoft.com <br>2. management.azure.com <br> 3. &#42;azurewebsites.net <br> 4. &#42;scm.azurewebsites.net<br>5. api.nuget.org/v3/index.json <br>6. msvsmon | 1. protokolu https <br>2. protokolu https  <br>3. http <br>4. protokolu https <br>5. protokol https <br>6. Concord <br> | 1. 443<br> 2. 443<br>3. 80  <br>4. 443<br> 5. 443<br> 6. 4022 (závislé verze sady visual Studio) | 1. Dotaz na soubor .json pro velikost SKU služby aplikace <br>2. Různé volání Azure RM <br>3. Volání zahřívání lokality prostřednictvím  <br>4. Zákazník je cílem koncový bod služby Kudu aplikace <br>5. Verze rozšíření lokality dotazu publikované v nuget.org <br>6. Vzdálené ladění kanálu |
|Azure Stream Analytics <br><br>HDInsight | Management.azure.com |protokol HTTPS|443 |Použít k zobrazení, odeslání, spouštět a spravovat úlohy ASA <br><br> Používá k procházení HDI clusterů a k odeslání, diagnostikovat a ladit HDI úlohy |
| Azure Data Lake | &#42;.azuredatalakestore.net <br>&#42;.azuredatalakeanalytics.net | protokol HTTPS | 443 | Používá ke kompilaci, odeslání, zobrazení, diagnostikovat a ladit úlohy; Umožňuje procházet soubory ADLS; použít k nahrávání a stahování souborů |
|Balení služby | [account].visualstudio.com <br/> [account].*.visualstudio.com <br/> *.blob.core.windows.net <br/> registry.npmjs.org </br> nodejs.org <br/> DIST.nuget.org <br/> Nuget.org | protokol HTTPS | 443 | *. Npmjs.org, *. nuget.org, a *. nodejs.org jsou jenom požadovaná pro určité scénáře úloh sestavení (například: Instalační program nástroje NuGet, instalační program nástroje uzlu) nebo pokud máte v úmyslu použít veřejné upstreams s informačních kanálů. Tři domény jsou požadovány pro základní funkce služby balení. |
|||||||

## <a name="troubleshoot-network-related-errors"></a>Řešení chyb související se sítí

V některých případech můžete spustit chyby související s sítí nebo proxy server při instalaci nebo použití sady Visual Studio za bránou firewall nebo proxy server. Další informace o řešení pro takový chybové zprávy, najdete v článku [řešení potíží s chybami související se sítí, když instalujete nebo použijte sadu Visual Studio](troubleshooting-network-related-errors-in-visual-studio.md) stránky.

## <a name="get-support"></a>Získat podporu

Zde jsou několik další možnosti podpory můžete:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Řešení potíží s chybami související se sítí v sadě Visual Studio](troubleshooting-network-related-errors-in-visual-studio.md)
* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
