---
title: Pokročilé funkce Visual Studio 2017
ms.date: 06/01/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e50bd5231387261e56a62234858d10c3806de3dc
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34694113"
---
# <a name="features-of-visual-studio-2017"></a>Funkce sady Visual Studio 2017

[Přehled Visual Studio IDE](../ide/visual-studio-ide.md) téma nabízí základní informace o sadě Visual Studio. Tento článek popisuje funkce, které může být vhodnější pro zkušeného vývojáře nebo uživatelů, kteří jsou již obeznámeni s Visual Studio.

## <a name="modular-installation"></a>Modulární instalace

Modulární instalační program sady Visual Studio můžete vybrat a nainstalovat *úlohy*, což jsou skupiny součástí, které jsou potřebné pro programovací jazyk nebo platformu dáváte přednost. Tato strategie pomáhá chránit otisk instalaci sady Visual Studio, která je menší, což znamená, nainstaluje se a aktualizací příliš rychlejší.

Pokud jste ještě nenainstalovali Visual Studio 2017, přejděte k [Visual Studio stáhne](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

Další informace o nastavení v systému Visual Studia, najdete v části [nainstalovat Visual Studio 2017](../install/install-visual-studio.md).

## <a name="create-cloud-enabled-apps-for-azure"></a>Vytváření aplikací využívajících cloud pro Azure.

Visual Studio nabízí sadu nástrojů, které vám umožní snadno vytvářet aplikace s povolenou podporu cloudu používá technologii Microsoft Azure. Můžete nakonfigurovat, vytvářet, ladit, balíčku a nasazení aplikací a služeb Microsoft Azure přímo z prostředí IDE. Chcete-li získat nástrojů Azure a šablony projektů, vyberte **Azure development** zatížení při instalaci sady Visual Studio.

![Vývoj pro Azure zatížení](../data-tools/media/azure-development-workload.png)

Po instalaci **Azure development** zatížení, následující **cloudu** jsou k dispozici v šablonách pro jazyk C# **nový projekt** dialogové okno:

![Šablony projektů cloudu pro sadu Visual Studio](media/cloud-project-templates.png)

Visual Studio [Průzkumník cloudu](/azure/vs-azure-tools-resources-managing-with-cloud-explorer) umožňuje zobrazit a spravovat prostředky na základě Azure cloud v sadě Visual Studio. Tyto prostředky může zahrnovat virtuální počítače, tabulek, databází SQL a další. **Cloud Explorer** ukazuje prostředky Azure v všechny účty spravované v rámci předplatného Azure se protokolují do. A pokud portál Azure, vyžaduje konkrétní operaci **Průzkumník cloudu** odkazy, které vás zavedou na portálu na místě, kde budete muset přejít.

![Průzkumník cloudu v sadě Visual Studio](media/cloud-explorer.png)

Můžete využít Azure services pro aplikace pomocí **připojené služby** jako například:

- [Připojení služby Active Directory](/azure/active-directory/develop/vs-active-directory-add-connected-service) tak uživatelé mohli používat své účty z [Azure Active Directory](/azure/active-directory/active-directory-whatis) pro připojení k webové aplikace
- [Úložiště Azure připojené služby](/azure/vs-azure-tools-connected-services-storage) pro úložiště objektů blob, fronty a tabulky
- [Připojení služby Key Vault](/azure/key-vault/vs-key-vault-add-connected-service) ke správě tajné klíče pro webové aplikace

K dispozici **připojené služby** závisí na typu vašeho projektu. Přidat službu kliknutím pravým tlačítkem myši na projekt v **Průzkumníku řešení** a výběr **přidat** > **připojení službě**.

![Visual Studio připojené služby](media/connected-services.png)

Další informace najdete v tématu [přesunout do cloudu s Visual Studio a Azure](https://www.visualstudio.com/vs/azure-tools/).

## <a name="create-apps-for-the-web"></a>Vytvoření aplikace pro web

Web jednotky naše moderní world a Visual Studio můžete usnadňuje psaní aplikací pro ni. Můžete vytvořit webové aplikace pomocí ASP.NET, Node.js, Python, JavaScript a TypeScript. Visual Studio rozumí webové platformy jako úhlová, jQuery, Express a další. Spuštěné na operačních systémech Windows, Mac a Linux .NET Core a ASP.NET Core. [ASP.NET Core](http://www.asp.net/core/overview) je hlavní aktualizace MVC, WebAPI a SignalR a běží na systému Windows, Mac a Linux.  ASP.NET Core má byly navrženy od základů až zajistit, že jste s .NET Štíhlá a bez možnosti složení zásobníku pro vytváření webových moderní cloudové aplikace a služby.

Další informace najdete v tématu [moderní webové nástroje](https://www.visualstudio.com/vs/modern-web-tooling/).

## <a name="build-cross-platform-apps-and-games"></a>Vytváření aplikací pro různé platformy a hry

Visual Studio můžete použít k vytvoření aplikace a hry pro systému macOS, Linux a Windows, a také pro Android, iOS a další [mobilní zařízení](https://www.visualstudio.com/vs/mobile-app-development/).

- Sestavení [.NET Core](/dotnet/core/) aplikace, které běží na systému Windows, systému macOS a Linux.

- Vytvoření mobilní aplikace pro iOS, Android a Windows v C# a F # pomocí [Xamarin](https://developer.xamarin.com/guides/cross-platform/windows/visual-studio/).

- Použijte standardní webové technologie&mdash;HTML, CSS a JavaScript&mdash;k vytváření mobilních aplikací pro iOS, Android a Windows pomocí [Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/).

- Sestavení 2D a 3D hry v jazyce C# s použitím [Visual Studio Tools for Unity](../cross-platform/visual-studio-tools-for-unity.md).

- Sestavení nativní C++ aplikace pro iOS, Android a Windows zařízení a společný kód sdílené složky v knihovnách vytvořené pro iOS, Android a Windows, a to pomocí [C++ pro vývoj pro různé platformy](../cross-platform/visual-cpp-for-cross-platform-mobile-development.md).

- Nasazení, testování a ladění aplikací pro Android pomocí [emulátoru Android](../cross-platform/visual-studio-emulator-for-android.md).

## <a name="connect-to-databases"></a>Připojení k databázím

**V Průzkumníku serveru** vám pomůže Procházet a spravovat instance systému SQL Server a prostředky místně, vzdáleně a na Azure, Salesforce.com, Office 365 a weby. Chcete-li otevřít **Průzkumníka serveru**, v hlavní nabídce zvolte **zobrazení** > **Průzkumníka serveru**. V tématu [přidat nová připojení](../data-tools/add-new-connections.md) pro další informace o použití Průzkumníka serveru.

[SQL Server Data Tools (SSDT)](/sql/ssdt/download-sql-server-data-tools-ssdt) je výkonný vývojové prostředí pro SQL Server, databáze SQL Azure a Azure SQL Data Warehouse. Umožňuje vytvářet, ladit, udržovat a Refaktorovat databáze. Můžete pracovat s projektem databáze, nebo přímo s připojené databáze instance nebo vypnout místně.

**Průzkumník objektů systému SQL Server** v sadě Visual Studio poskytuje zobrazení objektů databáze podobně jako SQL Server Management Studio. Průzkumník objektů systému SQL Server můžete pro účely správy a návrh lehká databáze, včetně úpravy dat v tabulce, porovnání schémat, provádění dotazů pomocí kontextové nabídky přímo z Průzkumníka objektů systému SQL Server a další.

![Průzkumník objektů systému SQL Server](../ide/media/vs2015_sqlobjectexplorer.png)

## <a name="debug-test-and-improve-your-code"></a>Ladění, testování a zlepšit váš kód

Při psaní kódu, budete muset spustit a otestovat ho chyb a výkonu. Visual Studio nejmodernější ladění systému umožňuje ladit kód spuštěný ve vašem místním projektu, na vzdáleném zařízení nebo na [zařízení emulátoru](../cross-platform/visual-studio-emulator-for-android.md). Můžete krok prostřednictvím kódu jeden příkaz v čase a průběžně kontrolovat proměnné. Můžete nastavit zarážky, které jsou pouze dosáhl při splnění zadané podmínky. Všechny tyto se dají spravovat editoru kódu, samostatně, takže nemusíte opustit váš kód. Chcete-li získat další informace o ladění v sadě Visual Studio, najdete v části [ladicího programu prohlídka funkce](../debugger/debugger-feature-tour.md).

Další informace o zvýšení výkonu aplikací, najdete v článku věnovaném se Visual Studio [profilace](../profiling/profiling-feature-tour.md) funkce.

Pro [testování](../test/improve-code-quality.md), Visual Studio nabízí testování částí, Live testování částí, IntelliTest, zátěže a testování výkonu a další. Visual Studio také obsahuje rozšířené [analýza kódu](../code-quality/code-analysis-for-managed-code-overview.md) možnosti k zachycení návrhu, zabezpečení a jiné typy nedostatky.

## <a name="deploy-your-finished-application"></a>Nasazení aplikace bylo dokončeno

Když je aplikace připravená k nasazení na uživatele nebo zákazníků, Visual Studio poskytuje nástroje k tomu, jestli nasazujete na Microsoft Store, na web služby SharePoint, nebo s technologiemi InstallShield nebo instalační služba systému Windows. Je přístupné pomocí rozhraní IDE. Další informace najdete v tématu [nasazení aplikací, služeb a komponent](../deployment/deploying-applications-services-and-components.md).

## <a name="manage-your-source-code-and-collaborate-with-others"></a>Správa zdrojového kódu a spolupracovat s ostatními

Můžete spravovat vašeho zdrojového kódu v hostované všechny zprostředkovatele, včetně Githubu úložiště Git. Nebo použijte [Visual Studio Team Services (VSTS)](/vsts/index) ke správě kód společně se chyby a pracovní položky pro celý projekt. V tématu [začít pracovat s Git a Team Services (služby VSTS)](/vsts/git/gitquickstart?tabs=visual-studio) Další informace o správě úložiště Git v sadě Visual Studio pomocí Team Explorer. Visual Studio má také další funkce integrované zdroj ovládacího prvku. Další informace o nich najdete v tématu [Git nové funkce v aplikaci Visual Studio 2017 (blog)](https://blogs.msdn.microsoft.com/visualstudioalm/2017/03/06/new-git-features-in-visual-studio-2017/).

Visual Studio Team Services je Cloudová služba pro hostování projektů softwaru a povolení spolupráce v týmy. Služby VSTS podporuje systémy Git a Team Foundation zdrojového kódu, jakož i metodiky Scrum a Agile a CMMI vývoj. Team Foundation verze ovládacího prvku (TFVC) používá jedinou, centralizovanou server úložiště ke sledování a verze souborů. Místní změny jsou vždy změnami na centrálním serveru, kde můžete jinými vývojáři získání nejnovějších změn.

Team Foundation Server (TFS) je Centrum správy životního cyklu aplikace Visual Studio. Umožňuje everyone spojené s procesu vývoje se zúčastnit pomocí jednoho řešení. TFS je užitečné pro správu heterogenní týmy a projekty, příliš.

Pokud máte účet Visual Studio Team Services nebo Team Foundation Server v síti, můžete se připojit k němu prostřednictvím **Team Explorer** oken v sadě Visual Studio. Z tohoto okna můžete zkontrolovat kód do nebo z zdrojového kódu, správě pracovních položek, sestavení a spuštění přístup týmové místnosti a pracovní prostory. Můžete otevřít **Team Explorer** z **Snadné spuštění** pole, nebo v hlavní nabídce z **zobrazení** > **Team Explorer** nebo z **Team** > **Správa připojení**.

Na následujícím obrázku **Team Explorer** okna pro řešení, který je hostován v služby VSTS.

![Visual Studio Team Explorer](../ide/media/vs2017_teamexplorer.png)

Můžete také automatizovat vašeho procesu sestavení vytvářet kód, který jste zkontrolovali devs ve vašem týmu do správy verzí. Lze například sestavit jeden nebo více projektů v noci nebo pokaždé, když je kód vrácen se změnami. Další informace najdete v tématu [sestavení a verze (služby VSTS a sady TFS)](/vsts/build-release/index).

## <a name="extend-visual-studio"></a>Rozšíření sady Visual Studio

Pokud Visual Studio nemá přesný funkce, které potřebujete, můžete ho přidat! Přizpůsobení integrovaného vývojového prostředí na základě vašeho pracovního postupu a styl, přidat podporu pro externí nástroje ještě integrované pomocí sady Visual Studio a upravit stávající funkce zvyšuje produktivitu. Nejnovější verzi Visual Studio Extensibility Tools (VS SDK), najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Kompilátoru platformu .NET ("Roslyn") můžete použít k zápisu vlastní analyzátorů kódu a generátory kódu. Najít všechno, co potřebujete v [Roslyn](https://github.com/dotnet/Roslyn).

Najít [existující rozšíření](https://marketplace.visualstudio.com/vs) pro sadu Visual Studio vytvořené vývojáři Microsoftu a také naše komunita vývoj.

Další informace o rozšíření sady Visual Studio najdete v tématu [rozšíření Visual Studio IDE](https://www.visualstudio.com/vs/extend/).

## <a name="see-also"></a>Viz také:

- [Přehled Visual Studio IDE](../ide/visual-studio-ide.md)
- [Co je nového ve Visual Studio 2017](../ide/whats-new-in-visual-studio.md)