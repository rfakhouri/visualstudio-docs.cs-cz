---
title: Instalace a použití za bránou firewall nebo proxy server
description: Zkontrolujte adresy URL, porty a protokoly, které byste mohli chtít přidat do seznamu povolených adres, nebo je otevřete, pokud vaše organizace používá bránu firewall nebo proxy server
ms.date: 05/22/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: ac150e20b505a5ef4446e77761790a6111fb6c10
ms.sourcegitcommit: 9c07ae6fb18204ea080c8248994a683fa12e5c82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2019
ms.locfileid: "70293514"
---
# <a name="install-and-use-visual-studio-and-azure-services-behind-a-firewall-or-proxy-server"></a>Instalace a používání sady Visual Studio a služeb Azure za bránou firewall nebo proxy serverem

Pokud vy nebo vaše organizace používáte bezpečnostní opatření, jako je brána firewall nebo proxy server, pak jsou k dispozici adresy URL domény, které byste mohli chtít přidat do seznamu povolených portů a porty a protokoly, které byste mohli chtít otevřít, abyste měli k dispozici nejlepší prostředí při instalaci a používání nástroje.  Visual Studio a služby Azure.

* **[Instalace sady Visual Studio](#install-visual-studio)** : Tyto tabulky obsahují adresy URL domény, které se mají přidat do seznamu povolených adres, abyste měli přístup ke všem komponentám a úlohám, které chcete.

* **[Používejte Visual Studio a služby Azure](#use-visual-studio-and-azure-services)** : Tato tabulka obsahuje adresy URL domény, které se mají přidat do seznamu povolených položek a porty a protokoly, které se mají otevřít, abyste měli přístup ke všem funkcím a službám, které chcete.

> [!NOTE]
> Tento článek byl napsán pro sadu Visual Studio na Windows, ale některé informace platí také pro [instalace sady Visual Studio pro Mac](/visualstudio/mac/install-behind-a-firewall-or-proxy-server) za bránou firewall nebo proxy serverem.

## <a name="install-visual-studio"></a>Instalace sady Visual Studio

### <a name="urls-to-add-to-an-allow-list"></a>Adresy URL, které se mají přidat do seznamu povolených

Vzhledem k tomu, že Instalační program pro Visual Studio stahuje soubory z různých domén a jejich serverů pro stahování, tady jsou adresy URL domény, které byste mohli chtít přidat do seznamu povolených položek jako důvěryhodné v uživatelském rozhraní nebo ve skriptech nasazení.

#### <a name="microsoft-domains"></a>Microsoft domains

| Domény | Účel |
| - | - |
| go.microsoft.com | Nastavení adresy URL řešení |
| aka.ms | Nastavení adresy URL řešení |
| download.visualstudio.microsoft.com | Nastavit umístění stahování balíčků |
| download.microsoft.com | Nastavit umístění stahování balíčků |
| download.visualstudio.com | Nastavit umístění stahování balíčků |
| dl.xamarin.com | Nastavit umístění stahování balíčků |
| marketplace.visualstudio.com | Umístění pro stahování rozšíření sady Visual Studio |
| VisualStudio.microsoft.com | Dokumentace k umístění |
| docs.microsoft.com | Dokumentace k umístění |
| msdn.microsoft.com | Dokumentace k umístění |
| WWW\.webu microsoft.com | Dokumentace k umístění |
| \*. windows.net | Místo přihlášení |
| \*. microsoftonline.com | Místo přihlášení |
| \*. live.com | Místo přihlášení |
| | |

#### <a name="non-microsoft-domains"></a>Domény od jiných výrobců

| Domény | Nainstaluje tyto úlohy |
| - | - |
| archive.apache.org | Vývoj mobilních aplikací pomocí jazyka JavaScript (Cordova) |
| cocos2d-x.org | Vývoj her v C++ (Kokosové ostrovy) |
| download.epicgames.com | Vývoj her v C++ (Unreal Engine) |
| download.oracle.com | Vývoj mobilních aplikací pomocí jazyka JavaScript (Java SDK) <br /><br />Vývoj mobilních aplikací pomocí .NET (Java SDK) |
| download.unity3d.com | Vývoj her pomocí Unity (Unity) |
| netstorage.unity3d.com | Vývoj her pomocí Unity (Unity) |
| dl.google.com | Vývoj mobilních aplikací pomocí jazyka JavaScript (sady Android SDK a sada NDK, emulátor) <br /><br />Vývoj mobilních aplikací pomocí .NET (sady Android SDK a sada NDK, emulátor) |
| WWW\.incredibuild.com | Vývoj her v C++ (IncrediBuild) |
| incredibuildvs2017i.azureedge.net | Vývoj her v C++ (IncrediBuild) |
| WWW\.python.org | Vývoj v jazyce Python (Python) <br /><br />Pro datové vědy a analytické aplikace (Python) |
| | |

## <a name="use-visual-studio-and-azure-services"></a>Použijte sadu Visual Studio a službami Azure

### <a name="urls-to-add-to-an-allow-list-and-ports-and-protocols-to-open"></a>Adresy URL, které se mají přidat do seznamu povolených a portů a protokolů k otevření

Pokud chcete mít jistotu, že máte přístup ke všemu, co potřebujete, když používáte Visual Studio nebo služby Azure za bránou firewall nebo proxy server, tady jsou adresy URL, které byste měli přidat do seznamu povolených položek, a porty a protokoly, které byste mohli chtít otevřít.

| Služba nebo scénáři | Koncový bod DNS | Protokol | Port | Popis |
| - | - | - | - | - |
| Adresa URL<br>rozlišení | go.microsoft.com<br><br>aka.ms | | | Používá ke zkrácení adresy URL, které se pak přeloží do delší adresy URL |
| Úvodní stránka | vsstartpage.blob.core.windows.net | | 443 | Slouží k zobrazení příspěvků vývojáře zobrazených na úvodní stránce (pouze Visual Studio 2017). |
| Cílem<br> Oznámení <br>Služba | targetednotifications.azurewebsites.net <br><br>www.research.net | | 80<br><br>443 | Slouží k filtrování globální seznam oznámení do seznamu, který se vztahuje pouze na konkrétní typy počítačů nebo použití scénáře |
| Rozšíření <br>Kontrola aktualizací | marketplace.visualstudio.com<br><br>&#42;.windows.net <br>&#42;.microsoftonline.com <br>&#42;.live.com | | 443 | Používá k poskytování oznámení, když má nainstalovaná rozšíření k dispozici aktualizace. <br><br> Použít jako umístění přihlášení |
| Projekt AI <br>Integrace | az861674.vo.msecnd.net | | 443<br> | Slouží ke konfiguraci nových projektů k odesílání dat o využití do účtu registrované služby Application Insights |
| Code Lens | codelensprodscus1su0.app.<br>codelens.visualstudio.com | | 443 | Použít k zadání informací v editoru o poslední aktualizace souboru, na časové ose změn, pracovní položky, které jsou přidružené změny, autory a další |
| Experimentální <br>povolení funkce | visualstudio-devdiv-c2s.msedge.net | | 80 | Použít k aktivaci experimentální nové funkce nebo funkce změny |
| Identita "oznámení" BADGE "" <br>(uživatelské jméno a avatara)<br>and <br>Nastavení roamingu | app.vssps.visualstudio.com <br><br>app.vsspsext.visualstudio.com<br><br>app.vssps.visualstudio.com<br><br> ns-sb2-prod-ch1-002.cloudapp.net <br><br>az700632.vo.msecnd.net | | 443 | Slouží k zobrazení jméno a avatara uživatele v prostředí IDE <br><br> Používá k zajištění toho, že změny nastavení přesouvat z jednoho počítače do jiného |
| Nastavení vzdáleného přístupu | az700632.vo.msecnd.net | | 443 | Umožňuje vypnout rozšíření, které způsobují problémy v sadě Visual Studio |
| Nástroje pro Windows | developer.microsoft.com <br><br>dev.windows.com  <br><br>appdev.microsoft.com | protokol HTTPS | 443 | Používá pro scénáře Windows app store |
| Schéma JSON <br>Zjišťování <br><br>Schéma JSON <br>Definice<br><br>Schéma JSON <br>Podpora pro <br>Prostředky Azure | json.schemastore.org <br>schemastoreorg.azurewebsites.net<br><br>json-schema.org<br><br>schema.management.azure.com | http<br>protokol HTTPS<br><br>http<br><br>protokol HTTPS | 80<br>443 <br><br> 443<br><br>443 | Umožňuje vyhledat a stáhnout schémat JSON, které může uživatel používat při úpravách dokumentů JSON <br><br>Používá k získání meta-schéma pro formát JSON<br><br>Používá k získání aktuálního schématu pro šablony nasazení Azure Resource Manageru |
| Balíček NPM <br>zjištění | Skimdb.npmjs.com <br><br>Registry.npmjs.org <br><br>Api.npms.io | protokol HTTPS<br><br>HTTP/s<br><br>protokol HTTPS | 443<br><br>80/443<br><br>443 | Vyžaduje se pro vyhledávání balíčků NPM a použitý k instalaci balíčku skriptu na straně klienta v webové projekty |
| Balíčků bower<br> ikony<br><br>Balíčků bower <br>search | Bower.IO <br><br>bowercache.azurewebsites.net <br>go.microsoft.com <br>Registry.bower.IO | http<br><br>protokol HTTPS<br>http<br>protokol HTTPS | 80<br><br>443<br>80<br>443 | Poskytuje výchozí ikonu balíčku bower  <br><br>Umožňuje vyhledat balíčky Bower |
| NuGet<br><br>Balíček NuGet<br> zjištění | API.nuget.org <br>www.nuget.org <br>Nuget.org<br><br>crl3.digicert.com <br>crl4.digicert.com <br>ocsp.digicert.com <br>cacerts.digicert.com | protokol HTTPS<br><br>HTTP/s | 443<br><br>80/443<br> | Použít k ověření podepsané balíčky NuGet.<br><br>Vyžaduje se pro vyhledávání balíčků NuGet a verze |
| Informace o úložišti Githubu | api.github.com | protokol HTTPS | 443 | Vyžaduje se pro získání dalších informací o balíčky bower |
| Linterů Web | Eslint.org<br><br>www.Bing.com <br><br>www.coffeelint.org | http | 80 | |
| Cookiecutter<br>Průzkumník šablony<br>zjištění <br><br>Cookiecutter <br>Explorer project<br> Vytvoření | api.github.com <br>RAW.githubusercontent.com <br>go.microsoft.com<br><br>pypi.org <br> pypi.python.org | protokol HTTPS | 443<br> | Používá se ke zjišťování online šablon z našeho doporučeného informačního kanálu a z úložišť GitHubu. <br><br>Umožňuje vytvořit projekt z šablony cookiecutter, která vyžaduje jednorázovou podle potřeby instalaci Pythonu balíčku cookiecutteru z indexu balíčků Pythonu (PyPI) |
| Balíček Pythonu <br>zjištění<br><br>Balíček Pythonu <br>management<br><br>Nový <br>Python <br> projekt <br>šablony | pypi.org<br> <br>pypi.python.org <br>bootstrap.pypa.io<br><br>go.microsoft.com | protokol HTTPS | 443 | Umožňuje vyhledat balíčky pip<br><br>Umožňuje automaticky instalovat modul pip, pokud není nalezena <br><br>Používá se k překladu následujících nových šablon projektů Pythonu na adresy URL šablon cookiecutter:<br> -Projekt klasifikace<br>-Projekt clusteringu <br> -Projekt regrese <br> -PyGame využívající PyKinect <br> -Projekt Pyvot |
| Office web <br>doplněk <br> Manifest <br>Ověření <br>Služba | verificationservice.osi.office.net | protokol HTTPS | 443 | Používá se k ověření manifesty doplňků pro web Office |
| SharePoint a <br>Doplňky pro Office | sharepoint.com | protokol HTTPS | 443 | Používá k publikování a testování Sharepointu a Office Add-ins k Sharepointu Online |
| Správce pracovních postupů <br>Testování služby<br> Hostitel | | http | 12292 | Pravidlo brány firewall, která se automaticky vytvořily pro testování Sharepointových doplňků s pracovními postupy |
| Automaticky shromažďovat <br>spolehlivost statistiky <br>a další <br>Prostředí pro zákazníky <br>Programů zlepšování (uživatelů CEIP)<br> pro sadu Azure SDK a <br>nástroje SQL <br><br> | vortex.data.microsoft.com<br> <br>dc.services.visualstudio.com | protokol HTTPS | 443 | Používá k odeslání spolehlivost statistiky (při selhání a zablokování data) od uživatele společnosti Microsoft. Skutečné zhroucení nebo zablokování dumps budou odeslány stále, pokud je povoleno zasílání zpráv o chybách Windows; jenom statistické informace o potlačeno; <br>Umožňuje zobrazit vzory anonymní používání rozšíření Azure Tools SDK pro Visual Studio a vzorce používání SQL nástrojů sady Visual Studio |
| Visual Studio <br> Prostředí pro zákazníky <br>Program zlepšování softwaru a (uživatelů CEIP) <br><br>PerfWatson.exe | vortex.data.microsoft.com<br>dc.services.visualstudio.com<br>visualstudio-devdiv-c2s.msedge.net<br>az667904.vo.msecnd.net <br>scus-breeziest-in.cloudapp.net<br> | protokol HTTPS | 443 | Používá ke shromažďování anonymních vzorců používání a protokoly chyb <br><br>Slouží ke sledování problémů zablokování uživatelského rozhraní |
| Vytvoření a<br>Správa <br>Prostředky Azure | management.azure.com <br>management.core.windows.net | protokol HTTPS | 443 | Použít pro vytvoření Azure Websites nebo další prostředky pro podporu publikování webových aplikací Azure Functions a WebJobs |
| Publikování aktualizované webové nástroje <br>kontroly a rozšíření <br>Doporučení | marketplace.visualstudio.com | protokol HTTPS | 443 | Ke kontrole dostupnost aktualizovat nástroje pro publikování. Pokud je zakázané, se nemusí zobrazit potenciální doporučená rozšíření pro publikování na webu |
| Aktualizované prostředků Azure <br>Informace o vytvoření koncového bodu | \*.blob.core.windows.net | protokol HTTPS | 443 | Použít k aktualizaci koncových bodů použitých pro vytváření prostředků Azure pro určité služby Azure. Pokud je zakázané, poslední stáhnout nebo součástí koncového bodu, který se místo toho používají umístění |
| Vzdálené ladění a <br>Vzdálené profilování <br>Azure Websites | &#42;.cloudapp.net <br> &#42;.azurewebsites.net | | 4022 | Používá se pro připojení vzdáleného ladicího programu na Azure Websites. Pokud je zakázané, nebudou fungovat připojení vzdáleného ladicího programu na Azure Websites |
| Služby Active Directory <br>Graf | graph.windows.net | protokol HTTPS | 443 | Používají ke zřízení nových aplikací Azure Active Directory. Také používá zprostředkovatel připojené služby Office 365 MSGraph- |
| Služba Azure Functions <br>Aktualizace rozhraní příkazového řádku <br>Kontrola | functionscdn.azureedge.net | protokol HTTPS | 443 | Používá se pro kontrolu pro aktualizované verze Azure Functions CLI. Pokud je zakázané, kopie v mezipaměti (nebo kopii provádět součástí Azure Functions) rozhraní příkazového řádku se použije místo toho |
| Cordova | npmjs.org<br>gradle.org | HTTP/s | 80/443 | Protokol HTTP se používá pro Gradle stahování během sestavování; Protokol HTTPS se používá k zahrnout v projektech Cordova-Plugin |
| Průzkumník cloudu | 1. &#60;clusterendpoint&#62; <br>Service Fabric <br>2. &#60;koncový bod správy&#62;<br>Obecné cloudové Exp <br>3. &#60;koncový bod grafu&#62;<br>Obecné cloudové Exp<br>4. &#60;koncový bod účtu úložiště&#62;<br>Uzly úložiště <br>5. &#60;webu azure portal adresy URL&#62;<br>Obecné cloudové Exp <br>6. &#60;klíče trezoru koncových bodů&#62; <br>Uzly virtuálních počítačů Azure Resource Manageru<br>7. &#60;PublicIPAddressOfCluster&#62;<br>Service Fabric vzdálené ladění a trasování ETW | <br>1. protokol https<br>2. protokol https<br>3. protokol https<br>4. protokol https<br>5. protokol https<br>6. protokol https<br>7: tcp | 1. 19080<br>2. 443 <br>3. 443 <br>4. 443 <br>5. 443 <br>6. 443 <br>7. dynamické | 1. Příklad: test12.eastus.cloudapp.com<br>2. Načte odběry a načte a spravují prostředky Azure<br>3. Načte odběry služby Azure Stack<br>4. Spravuje prostředky úložiště (Příklad: mystorageaccount.blob.core.windows.net)<br>5. "Otevřít na portálu" možnost místní nabídky (prostředek se otevře na portálu Azure portal)<br>6. Vytváří a používá trezorům klíčů pro ladění virtuálního počítače (Příklad: myvault.vault.azure.net) <br><br>7. Dynamicky přiděluje blok porty podle počtu uzlů v clusteru a dostupných portů. <br><br>Port blokování se pokusí získat třikrát počet uzlů s minimálně 10 portů.<br><br>Pro trasování streamování je proveden pokus o získání portu blok z 810. Pokud některý z tohoto bloku port je již použit, je proveden pokus o získání další blok, a tak dále. (Nástroj pro vyrovnávání zatížení je prázdný, pak se pravděpodobně používají porty z 810) <br><br>Podobně pro ladění, jsou vyhrazené čtyři sady bloků porty: <br>- connectorPort: 30398, <br>- forwarderPort: 31398, <br>- forwarderPortx86: 31399,<br>- fileUploadPort: 32398<br> |
| Cloudové služby | 1. PROTOKOL RDP<br><br>2. core.windows.net <br><br>3. management.azure.com<br> management.core.windows.net <br><br>4. &#42;.blob.core.windows.net <br>&#42;.queue.core.windows.net<br>&#42;.table.core.windows.net <br><br>5. portal.azure.com <br><br>6. &#60;uživatele cloudovou službu&#62;. cloudapp.net <br> &#60;user's VM&#62;.&#60;region&#62;.azure.com | 1. rdp <br><br> 2. protokol https <br><br> 3. protokol https <br><br> 4. protokol https <br><br> 5. protokol https <br><br>6. tcp | 1. 3389 <br><br> 2. 443 <br><br> 3. 443 <br><br>4. 443 <br><br>5. 443 <br><br> 6.) 30398 <br> 6. b) 30400 <br> 6. c) 31398 <br> 6. d) 31400 <br> 6. e) 32398 <br> 6. f) 32400 | 1.  Vzdálená plocha ke Cloudovým službám virtuálního počítače <br><br> 2.  Součástí účtu úložiště diagnostiky privátní konfigurace <br><br> 3.  Azure portal <br><br> 4. Průzkumník serveru – Azure Storage &#42; je zákazník s názvem účtu úložiště  <br><br> 5.  Odkazy k otevření portálu &#47; stažení certifikátu předplatného &#47; soubor nastavení publikování <br><br>6.) konektoru místní port pro vzdálené ladění pro cloudovou službu a virtuálních počítačů<br> 6. b) konektoru veřejný port pro vzdálené ladění pro cloudovou službu a virtuálních počítačů <br> 6. c) předávání místní port pro vzdálené ladění pro cloudovou službu a virtuálních počítačů <br> 6. d) předávání veřejný port pro vzdálené ladění pro cloudovou službu a virtuálních počítačů  <br> 6. e) soubor uživatele nahrávajícího místní port pro vzdálené ladění pro cloudovou službu a virtuálních počítačů <br> 6. f) soubor uživatele nahrávajícího veřejný port pro vzdálené ladění pro cloudovou službu a virtuálních počítačů |
| Service Fabric | 1. <br>ocs.Microsoft.com<br>aka.ms <br>go.microsoft.com <br><br>2. <br>vssftools.blob.core.windows.net <br>Vault.azure.com <br>Portal.azure.com <br><br> 3. &#42; vault.azure.net<br><br> 4. <br>app.vsaex.visualstudio.com<br>&#42; .vsspsext.visualstudio.com<br>clouds.vsrm.visualstudio.com <br>clouds.visualstudio.com<br>app.vssps.visualstudio.com <br>&#42; .visualstudio.com | protokol HTTPS | 443 | 1. Dokumentace <br><br> 2. Vytvoření funkce clusteru <br><br>3. &#42; Je název služby Azure key vault (Příklad:-test11220180112110108.vault.azure.net  <br><br>  4. &#42; Je dynamický (Příklad: vsspsextprodch1su1.vsspsext.visualstudio.com) |
| Snímek <br>Ladicí program | 1. go.microsoft.com <br>2. management.azure.com <br> 3. &#42;azurewebsites.net <br> 4. &#42;scm.azurewebsites.net<br>5. api.nuget.org/v3/index.json <br>6. msvsmon (. exe) | 1. protokol https <br>2. protokol https  <br>3. http <br>4. protokol https <br>5. protokol https <br>6. Concord <br> | 1. 443<br> 2. 443<br>3. 80  <br>4. 443<br> 5. 443<br> 6. 4022 (závislé verze sady visual Studio) | 1. Dotazování soubor .json pro velikost SKU app service <br>2. Volání Azure RM <br>3. Volání zahřívání webu prostřednictvím  <br>4. Zákazník cílových koncového bodu aplikace App Service Kudu <br>5. Verze rozšíření webu dotazu publikované v nuget.org <br>6. Vzdálené ladění kanálu |
| Azure Stream Analytics <br><br>HDInsight | Management.azure.com | protokol HTTPS | 443 | Slouží k zobrazení, odeslání, spouštět a spravovat úlohy Azure Stream Analytics <br><br> Umožňuje procházet clusterů Hdinsight a odešlete, Diagnostika a ladění úloh HDI |
| Azure Data Lake | &#42;.azuredatalakestore.net <br>&#42;.azuredatalakeanalytics.net | protokol HTTPS | 443 | Použít ke kompilaci, odeslat, zobrazení, Diagnostika a ladění úloh; Umožňuje procházet soubory ADLS; použít k nahrávání a stahování souborů |
| Vytváření balíčků služby | [account].visualstudio.com <br/> [účet]. \*. visualstudio.com <br/> \*.blob.core.windows.net <br/> registry.npmjs.org </br> nodejs.org <br/> DIST.nuget.org <br/> Nuget.org | protokol HTTPS | 443 | Npmjs.org, \*. NuGet.org a \*. NodeJS.org jsou požadovány pouze pro některé scénáře úloh sestavení (například: \* Instalační program nástroje NuGet, instalační program nástroje uzlu) nebo pokud máte v úmyslu používat veřejné nadřazené služby s vašimi informačními kanály. Tři domény jsou požadovány pro základní funkce služby balení. |
| Služby Azure DevOps | \*. vsassets.io <br/> static2.sharepointonline.com <br/> dev.azure.com | | | Použít k připojení ke službám Azure DevOps |
| | | | | |

## <a name="troubleshoot-network-related-errors"></a>Řešení potíží s chybami související se sítí

V některých případech může být spustíte chyby související s sítě nebo proxy server při instalaci nebo používání sady Visual Studio za bránou firewall nebo proxy server. Další informace o řešeních pro tyto chybové zprávy najdete v tématu [při instalaci nebo používání sady Visual Studio, řešení potíží s chybami související se sítí](troubleshooting-network-related-errors-in-visual-studio.md) stránky.

## <a name="get-support"></a>Získat podporu

Nabízíme [ **živý chat** ](https://visualstudio.microsoft.com/vs/support/#talktous) (jenom v angličtině) možnost podpory pro problémy související s instalací.

Tady je několik dalších možností podpory:

* Hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio.md) nástroj, který se zobrazí v instalačním programu sady Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Navrhnout funkci sledování problémů s produktem a najít odpovědi v [komunity vývojářů v aplikaci Visual Studio](https://developercommunity.visualstudio.com/).
* Použití vaší [Githubu](https://github.com/) účet ke komunikaci s námi a dalších Visual Studio získávají vývojáři v [konverzace sady Visual Studio v komunitě Gitteru](https://gitter.im/Microsoft/VisualStudio).

## <a name="see-also"></a>Viz také:

* [Požadavky na připojení pro Live Share](/visualstudio/liveshare/reference/connectivity/)
* [Vytvoření síťové instalace sady Visual Studio](create-a-network-installation-of-visual-studio.md)
* [Řešení potíží s chybami související se sítí v sadě Visual Studio](troubleshooting-network-related-errors-in-visual-studio.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Nainstalovat za bránou firewall nebo proxy serverem (Visual Studio for Mac)](/visualstudio/mac/install-behind-a-firewall-or-proxy-server)
