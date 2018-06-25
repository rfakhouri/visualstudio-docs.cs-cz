---
title: Přehled nasazení – Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: overview
dev_langs:
- FSharp
- VB
- CSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7346de998052ba68dfadf74a09fe0d4339be1614
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757159"
---
# <a name="overview-of-deployment-in-visual-studio"></a>Přehled nasazení v sadě Visual Studio

Nasazením aplikace, služby nebo komponenty ji budete distribuovat pro instalaci na dalších počítačích, zařízeních, serverech nebo v cloudu. V sadě Visual Studio můžete zvolit vhodnou metodu pro potřebný typ nasazení.

Pro mnoho běžných typů aplikací můžete nasadit vaše právo aplikace v Průzkumníku řešení v sadě Visual Studio. Stručný přehled tato funkce, najdete v části [první pohled na nasazení](../deployment/deploying-applications-services-and-components.md).

![Vyberte možnost publikování](../deployment/media/quickstart-publish-azure.png)

## <a name="what-publishing-options-are-right-for-me"></a>Jaké možnosti publikování je pro mě nejlepší?

Z Visual Studia aplikace lze publikovat přímo na následující cíle:

- [Aplikační služba Azure](#azure-app-service)
- [Virtuální počítače Azure](#azure-virtual-machines)
- [Systém souborů](#file-system)
- [Vlastní cíle (služby IIS, FTP, atd.) ](#custom-targets), který zahrnuje všechny libovolné webové servery.

Na **publikovat** kartě můžete vybrat existující profil publikování, importovat existující nebo vytvořit novou pomocí možnosti popsané v tomto poli. Prohlídka možnosti publikování v integrovaném vývojovém prostředí pro různých typů aplikací, najdete v části [první pohled na nasazení](../deployment/deploying-applications-services-and-components.md).

## <a name="azure-app-service"></a>Aplikační služba Azure

[Aplikační služba Azure](/azure/app-service/app-service-web-overview) pomáhá vývojářům rychle vytvořit různé škálovatelných webových aplikací a služeb bez údržbu infrastruktury.

Můžete určit, kolik computing spotřeby APp Service má výběrem [cenová úroveň nebo se chystáte](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview) pro službu obsahující aplikaci. Může mít několik webových aplikací (a jinými typy aplikací) sdílet stejnou službu aplikace beze změny cenové úrovně. Například můžete hostovat vývoj, pracovní a provozní webové aplikace společně na stejném App Service.

App Service běží na hostovaných v cloudu virtuálních počítačů v Azure, ale jsou spravovaná tyto virtuální počítače. Každá aplikace v App Service bude přiřazen jedinečný \*. azurewebsites.net URL; všechny cenové úrovně než volné povolit přiřazení vlastních názvů domén do lokality.

### <a name="when-to-choose-azure-app-service"></a>Když chcete-li zvolit Azure App Service

- Chcete nasadit webovou aplikaci, která je přístupná prostřednictvím Internetu.
- Chcete automaticky škálovat podle požadavků webové aplikace bez nutnosti znovu nasadit.
- Nechcete udržovat infrastrukturu serveru (včetně aktualizací softwaru).
- Nepotřebujete žádné úpravy na úrovni počítače na serverech, které jsou hostiteli webové aplikace.

> Pokud chcete používat Azure App Service ve svém vlastním datovém centru nebo jiným počítačům v místě, můžete to udělat tak pomocí [zásobník Azure](https://azure.microsoft.com/overview/azure-stack/).

Další informace o publikování do služby App Service naleznete v tématu [rychlý start - publikování do služby Azure App Service](quickstart-deploy-to-azure.md).

## <a name="azure-virtual-machines"></a>Virtuální počítače Azure

[Virtuální počítače Azure (VM)](https://azure.microsoft.com/documentation/services/virtual-machines/) umožňují vytvářet a spravovat libovolný počet výpočetních prostředků v cloudu. Za předpokladu, odpovědnost za všechny softwaru a aktualizací na virtuálních počítačích, můžete je upravit tolik, kolik požadovaného podle požadavků vaší aplikace. Virtuální počítače můžete přistupovat přímo prostřednictvím vzdálené plochy, a také požadovaných každé z nich budou udržovat přiřazená IP adresa.

Škálování aplikace, která je hostovaná na virtuálních počítačích zahrnuje otáčí až další virtuální počítače podle požadavků a pak nasazení potřebný software. Tato další úroveň umožňuje ovládací prvek, je škálovat jinak v různých oblastech globální. Například pokud vaše aplikace je obsluhuje zaměstnanci v různých místní pobočky, je možné škálovat podle počtu zaměstnanců v těchto oblastech potenciálně snižuje tak náklady na virtuální počítače.

Další informace najdete v části [podrobné porovnání](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/) mezi Azure App Service, Azure Virtual Machines a jinými službami Azure, které můžete použít jako cíl nasazení pomocí možnosti vlastní v sadě Visual Studio.

### <a name="when-to-choose-azure-app-virtual-machines"></a>Když vyberte virtuální počítače Azure aplikace

- Chcete nasadit webovou aplikaci, která je přístupná prostřednictvím Internetu, s plnou kontrolu nad životnost přiřazené IP adresy.
- Je nutné přizpůsobení na úrovni počítače na serverech, což zahrnuje další software, například systém specializované databáze, konkrétní síťové konfigurace, diskových oddílů a tak dále.
- Chcete, aby dobře úroveň kontroly nad škálování webové aplikace.
- Musíte přímý přístup k serverům hostování vaší aplikace z jiného důvodu.

> Pokud chcete používat virtuální počítače Azure ve svém vlastním datovém centru nebo jiným počítačům v místě, můžete provést tak pomocí [zásobník Azure](https://azure.microsoft.com/overview/azure-stack/).

## <a name="file-system"></a>Systém souborů

Nasazení do systému souborů znamená jednoduše zkopírovat soubory vaší aplikace do konkrétní složky ve vašem počítači. Tato možnost se nejčastěji používá pro účely testování nebo pro nasazení aplikací pro použití v omezený počet lidí, pokud počítač běží serveru. Pokud cílová složka je sdílena v síti, pak nasazení do systému souborů můžete zpřístupnit webové aplikace soubory ostatním uživatelům, kteří mohou poté ji nasadit do konkrétních serverů.

Všechny místní počítače, které běží serveru můžete zpřístupnit aplikaci prostřednictvím Internetu nebo intranetu v závislosti na tom, jak je nakonfigurovaná a sítě, ke kterým je připojen. (Pokud se počítač připojit přímo k Internetu, buďte opatrní hlavně k ochraně před externí ohrožení zabezpečení.) Vzhledem k tomu, že budete spravovat tyto počítače, můžete začít úplnou kontrolu nad softwarových a hardwarových konfiguracích.

Všimněte si, že pokud z nějakého důvodu (například přístup k počítači) nejste moci používat cloudové služby, jako je Azure App Service nebo virtuálních počítačích Azure, můžete použít [zásobník Azure](https://azure.microsoft.com/overview/azure-stack/) ve svém vlastním datovém centru. Zásobník Azure umožňuje spravujete a používáte výpočetních prostředků pomocí Azure App Service a Azure Virtual Machines zachováním ještě všechno místně.

### <a name="when-to-choose-file-system-deployment"></a>Kdy použít nasazení systému souborů

- Potřebovat pouze nasazení aplikace do sdílené složky, ze kterého ostatní nasadí ho na různé servery.
- Je nutné pouze místní testovací nasazení.
- Chcete prozkoumat a upravit soubory aplikace potenciálně nezávisle před jejich odesláním na jiný cíl nasazení.

Další informace najdete v tématu [rychlý start - nasazení do místní složky](quickstart-deploy-to-local-folder.md)

## <a name="custom-targets-iis-ftp"></a>Vlastní cíle (služby IIS, FTP)

Vlastní cíl umožňuje nasazení aplikace na cíl, než Azure App Service, virtuální počítače Azure nebo místního systému souborů. Můžete nasadit systém souborů nebo jiný server (Internetu nebo intranetu) ke kterému máte přístup, včetně těch, na jiných cloudových služeb. Můžete pracovat s web nasazení (soubory nebo. ZIP) a FTP.

Při výběru vlastní cíl, Visual Studio vás vyzve k zadání názvu profilu a pak shromažďovat další **připojení** informace, včetně na cílový server nebo umístění, název lokality a přihlašovací údaje. Můžete řídit následujících chování na **nastavení** karty:

- Konfigurace, které chcete nasadit.
- Jestli chcete odebrat existující soubory z cílového umístění.
- Určuje, zda předkompilovat během publikování.
- Určuje, zda chcete vyloučit soubory ve složce App_Data z nasazení.

Můžete vytvořit libovolný počet vlastní profily nasazení v sadě Visual Studio, které umožňují spravovat profily s jiným nastavením.

### <a name="when-to-choose-custom-deployment"></a>Kdy použít vlastní nasazení

- Cloudové služby používáte na zprostředkovateli než Azure, která je přístupná prostřednictvím adresy URL.
- Chcete nasadit, pomocí přihlašovacích údajů než ty, které používáte v sadě Visual Studio, nebo těch, které přímo navázána na vaše účty Azure.
- Chcete odstranit soubory z cíle pokaždé, když nasazujete.

Další informace najdete v tématu [rychlý start - nasazení do webové stránky](quickstart-deploy-to-a-web-site.md)

## <a name="next-steps"></a>Další kroky

Kurzy:

- [Nasazení aplikace .NET Core pomocí nástroje publikování](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Publikování aplikace jádro ASP.NET pro Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Nasazení ve Visual C++](/cpp/ide/deployment-in-visual-cpp)
- [Nasazení aplikací UWP](/windows/uwp/packaging/packaging-uwp-apps?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Publikování aplikace Node.js do Azure pomocí nástroje nasazení webu](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Publikování aplikace Python do Azure App Service](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
