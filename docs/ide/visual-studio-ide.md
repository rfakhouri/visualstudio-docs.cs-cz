---
title: Přehled Visual Studio 2017
ms.date: 02/05/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- MSDNSTART
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0fdc6acd2c14331d34ccb3f3435b1ee5fcc44a14
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="visual-studio-ide-overview"></a>Přehled Visual Studio IDE

Visual Studio interaktivní vývojové prostředí (IDE) je tvůrčí odrazový můstek, můžete zobrazit a upravit téměř všechny typy kódu a pak ladění, vytvářet a publikovat aplikace pro Android, iOS, Windows, na webu a cloudem. Nejsou k dispozici pro Mac a Windows verze. Toto téma vás seznámí s funkcí Visual Studio IDE. Projdeme některé věci, můžete pomocí sady Visual Studio a jak nainstalovat a používat ji, vytvoření jednoduché projektu, získání ukazatele na nasazení a ladění kódu a prohlídka různé nástroje Windows.

## <a name="what-can-you-do-with-the-visual-studio-ide"></a>Co se děje s Visual Studio IDE?

Chcete vytvořit aplikaci pro Android phone? Můžete to udělat. O tom, jak vytvořit špičkových hry s použitím C++? Můžete to udělat příliš a mnohem, mnohem víc. Visual Studio poskytuje šablony, které vám pomohou provést weby, hry, aplikace klasické pracovní plochy, mobilní aplikace, aplikace pro Office a další.

![Projekty Visual Studio](../ide/media/VSIDE_Tour_Projects_List.png)

Nebo můžete jednoduše otevřít některé kódu můžete získat z téměř odkudkoli a získat práce. Zobrazit projektu na Githubu, která se vám líbí? Právě klonovat úložiště, otevřete v sadě Visual Studio a psaní!

### <a name="create-mobile-apps"></a>Vytvoření mobilní aplikace

Můžete vytvořit nativní mobilních aplikací pro různé platformy pomocí jazyka C# a Xamarin nebo Visual C++, nebo hybridní aplikace pomocí jazyka JavaScript pomocí Apache Cordova. Můžete napsat mobilní hry pro Unity, nerealiz, DirectX, Kokosové a další. Visual Studio obsahuje emulátoru Androidu můžete spustit a ladění aplikací pro Android.

Výkon cloudu můžete využít pro své mobilní aplikace tak, že vytvoříte Azure aplikace služby. Azure app services povolit vaše aplikace ukládat data do cloudu, bezpečně ověřování uživatelů a automaticky škálovat své prostředky nebo dolů na vyhovovaly potřebám vaší aplikace a firmu. Další informace najdete v tématu [vývoj mobilních aplikací](https://www.visualstudio.com/vs/mobile-app-development/).

### <a name="create-cloud-apps-for-azure"></a>Vytvoření cloudové aplikace pro Azure.

Visual Studio nabízí sadu nástrojů, které vám umožní snadno vytvářet aplikace s povolenou podporu cloudu používá technologii Microsoft Azure. Můžete nakonfigurovat, vytvářet, ladit, balíčku a nasazení aplikací a služeb Microsoft Azure přímo z prostředí IDE. Chcete-li získat nástroje Azure pro .NET, vyberte **Azure development** zatížení při instalaci sady Visual Studio. Další informace najdete v tématu [Visual Studio Tools for Azure](https://www.visualstudio.com/vs/azure-tools/).

Můžete využít Azure services pro aplikace pomocí připojení služby, jako třeba:

- [Azure Mobile Services](http://azure.microsoft.com/documentation/services/mobile-services/)

- [Azure Storage](http://azure.microsoft.com/documentation/services/storage/)

[HockeyApp](https://www.visualstudio.com/hockey-app/) pomáhá distribuovat beta verze, shromažďování sestavy havárií za provozu a získávat zpětnou vazbu od skutečné uživatele. Kromě toho můžete integrovat rozhraní REST API Office 365 do vlastní aplikace pro připojení k data uložená v cloudu. Další informace najdete v tématu [tyto ukázky Githubu](https://github.com/OfficeDev/?utf8=%E2%9C%93&query=o365).

[Application Insights](https://marketplace.visualstudio.com/items?itemName=VisualStudioOnlineApplicationInsights.application-insights) pomáhá rozpoznat a diagnostikovat problémy kvality ve svých aplikacích a webové služby. Application Insights také pomáhá pochopit, co uživatelé ve skutečnosti provádějí s vaší aplikací, takže můžete optimalizovat uživatelské prostředí.

### <a name="create-apps-for-the-web"></a>Vytvoření aplikace pro web

Web jednotky naše moderní world a Visual Studio můžete usnadňuje psaní aplikací pro ni. Můžete vytvořit webové aplikace pomocí ASP.NET, Node.js, Python, JavaScript a TypeScript. Visual Studio rozumí webové platformy jako úhlová, jQuery, Express a další. Spuštěné na operačních systémech Windows, Mac a Linux .NET Core a ASP.NET Core. [ASP.NET Core](http://www.asp.net/core/overview) je hlavní aktualizace MVC, WebAPI a SignalR a běží na systému Windows, Mac a Linux.  ASP.NET Core má byly navrženy od základů až zajistit, že jste s .NET Štíhlá a bez možnosti složení zásobníku pro vytváření webových moderní cloudové aplikace a služby.

Další informace najdete v tématu [moderní webové nástroje](https://www.visualstudio.com/vs/modern-web-tooling/).

### <a name="build-cross-platform-apps-and-games"></a>Vytváření aplikací pro různé platformy a hry

Visual Studio můžete použít k vytvoření aplikace a hry pro systému macOS, Linux a Windows, a také pro Android, iOS a jiných mobilních zařízení.

- Sestavení [.NET Core](/dotnet/core/) aplikace, které běží na systému Windows, systému macOS a Linux.

- Vytvoření mobilní aplikace pro iOS, Android a Windows v C# a F # pomocí [Xamarin](https://developer.xamarin.com/guides/cross-platform/windows/visual-studio/).

- Použijte standardní webové technologie&mdash;HTML, CSS a JavaScript&mdash;k vytváření mobilních aplikací pro iOS, Android a Windows pomocí [Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/).

- Sestavení 2D a 3D hry v jazyce C# s použitím [Visual Studio Tools for Unity](../cross-platform/visual-studio-tools-for-unity.md).

- Sestavení nativní C++ aplikace pro iOS, Android a Windows zařízení a společný kód sdílené složky v knihovnách vytvořené pro iOS, Android a Windows, a to pomocí [C++ pro vývoj pro různé platformy](../cross-platform/visual-cpp-for-cross-platform-mobile-development.md).

- Nasazení, testování a ladění aplikací pro Android pomocí [emulátoru Android](../cross-platform/visual-studio-emulator-for-android.md).

Visual Studio, můžete to udělat celou řadu věcí další pomoc. Získat úplný seznam najdete v tématu [www.visualstudio.com](https://www.visualstudio.com/vs/).

## <a name="install-the-visual-studio-ide"></a>Instalace sady Visual Studio IDE

Pokud chcete začít, stáhněte si Visual Studio a nainstalujte ho do systému. Tuto součást můžete stáhnout na [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

Visual Studio je nyní jednodušší než kdy dřív. Modulární instalační program vám umožňuje vybrat a nainstalovat *úlohy*, což jsou skupiny součástí, které jsou potřebné pro programovací jazyk nebo platformu dáváte přednost. Tato strategie pomáhá udržovat nároků instalace Visual Studia, která je menší než kdy dřív, což znamená, nainstaluje se a aktualizuje rychlejší příliš. Kromě instalace lepší výkon má Visual Studio 2017 také kratší spuštění IDE a načíst dobu řešení.

Další informace o nastavení v systému Visual Studia, najdete v části [nainstalovat Visual Studio 2017](../install/install-visual-studio.md). Podle pokynů pro [vytváření program](#create-a-program), je nutné vybrat **vývoj pro různé platformy .NET Core** zatížení během instalace.

![Instalační program pro Visual Studio](../ide/media/overview-net-core-workload.png)

## <a name="sign-in"></a>Přihlásit se

Při prvním spuštění sady Visual Studio, můžete volitelně Přihlaste se pomocí účtu Microsoft nebo váš pracovní nebo školní účet. Probíhá přihlašování umožňuje synchronizovat nastavení sady Visual Studio, například rozložení oken v různých zařízeních. Je také jste se automaticky připojí k služby může být nutné, jako je například předplatných Azure a [Visual Studio Team Services](/vsts/).

## <a name="create-a-program"></a>Vytvořit program

Další informace o něco jeden vhodný způsob je pro použití! Umožňuje podrobné informace a vytvořit nové, jednoduchý program.

1. Otevřete Visual Studio. V nabídce zvolte **soubor** > **nový** > **projektu**.

  ![Soubor > Nový projekt v řádku nabídek](../ide/media/VSIDE_Tour_NewProject1.png)

1. **Nový projekt** dialogové okno zobrazí několik šablon projektu. Vyberte **.NET Core** kategorii v **Visual C#** a potom zvolte **konzolové aplikace (.NET Core)** šablony. V **název** textové pole, zadejte "Hello World". Vyberte **OK** tlačítko.

  ![Šablony aplikace .NET core](../ide/media/overview-new-project-dialog.png)

  > [!NOTE]
  > Pokud nevidíte **.NET Core** kategorie, je třeba nainstalovat **vývoj pro různé platformy .NET Core** zatížení. To pokud chcete udělat, vyberte **otevřete instalační program Visual Studio** odkaz na spodní levé straně **nový projekt** dialogové okno. Po **instalační program Visual Studio** otevře, posuňte se dolů a vyberte **vývoj pro různé platformy .NET Core** zatížení a potom zvolte **upravit**.

   Visual Studio používá šablonu pro vytvoření projektu. Je jednoduchou aplikaci "Hello World", která volá <xref:System.Console.WriteLine> metodu pro zobrazení řetězcového literálu "Hello, World!" v okně konzoly.

1. Zanedlouho byste měli vidět něco podobného jako na následujícím snímku obrazovky:

  ![Visual Studio – sada IDE](../ide/media/overview-ide-console-app.png)

   Kód jazyka C# pro vaši aplikaci se zobrazí v okně editor, které zabírají většina místa. Všimněte si, že syntaxe kódu je automaticky obarvené udávajících různé typy kódu, jako jsou klíčová slova a typy. Kromě toho malé, svislá přerušované čáry v kódu označují, které složené závorky odpovídat navzájem a čísla řádků vám pomohou vyhledat kód později. Můžete použít znaky minus malé, zabalené sbalit nebo rozbalte kódu. Tento kód osnovy funkce umožňuje skrýt kódu, které nepotřebujete, pomáhá minimalizovat zbytečné soubory na obrazovce.

   Soubory projektu, které jsou uvedené na pravé straně v okně názvem **Průzkumníku řešení**.

  ![Visual Studio IDE s červenou polí](../ide/media/overview-ide-console-app-red-boxes.png)

  Existují jiné nabídky a nástroje systému windows k dispozici, ale umožňuje přesun chvíli.

1. Nyní spusťte aplikaci. To provedete tak, že zvolíte **spustit bez ladění** z **ladění** nabídky v řádku nabídek. Můžete také stisknout **Ctrl**+**F5**.

  ![Ladění > Spustit bez ladění nabídky](../ide/media/overview-start-without-debugging.png)

  Visual Studio vytvoří aplikaci a otevře se okno konzoly se zprávou "Hello, World!". Nyní máte spuštěné aplikaci!

  ![Okno konzoly](../ide/media/overview-console-window.png)

1. Zavřete okno konzoly, stisknutím libovolné klávesy.

1. Přidejme nějaký další kód do aplikace. Přidejte následující C# kód před řádek, která uvádí, že `Console.WriteLine("Hello World!");`:

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   Tento kód zobrazí "Jaký je název vaší?" v konzole okno a počká, dokud uživatel nezadá nějaký text následuje **Enter** klíč.

1. Teď změňte řádek, která uvádí, že `Console.WriteLine("Hello World!");` na následující kód:

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. Znovu spusťte aplikaci tak, že vyberete **ladění** > **spustit bez ladění** nebo stisknutím kombinace kláves **Ctrl**+**F5**.

   Visual Studio znovu sestaví aplikace a otevře okno konzoly a vás vyzve k zadání vaše jméno.

1. Zadejte název v okně konzoly a stiskněte klávesu **Enter**.

   ![Vstup okna konzoly](media/overview-console-input.png)

1. Stisknutím libovolné klávesy zavřete okno konzoly.

## <a name="debug-test-and-improve-your-code"></a>Ladění, testování a zlepšit váš kód

Nic spustí perfektně vždy. Při psaní kódu, budete muset spustit a otestovat ho chyb a výkonu. Visual Studio špičkových ladění systému umožňuje ladit kód spuštěný ve vašem místním projektu, na vzdáleném zařízení nebo na emulátoru, jako [pro zařízení se systémem Android](../cross-platform/visual-studio-emulator-for-android.md). Můžete krok prostřednictvím kódu jeden příkaz v čase a průběžně kontrolovat proměnné. Můžete nastavit zarážky, které jsou pouze dosáhl při splnění zadané podmínky. Můžete sledovat hodnoty proměnných, jako je kód spuštěn a další. Všechny tyto se dají spravovat editoru kódu, samostatně, takže nemusíte opustit váš kód. Chcete-li získat další informace o ladění v sadě Visual Studio, najdete v části [ladicího programu prohlídka funkce](../debugger/debugger-feature-tour.md).

Pro testování, Visual Studio nabízí testování, IntelliTest, zátěže a testování výkonu a další jednotky. Další informace o testování najdete v tématu [testování nástroje a scénáře](../test/developer-testing-scenarios.md). Další informace o zvýšení výkonu aplikací, najdete v části [profilace prohlídka funkce](../profiling/profiling-feature-tour.md).

## <a name="deploy-your-finished-application"></a>Nasazení aplikace bylo dokončeno

Když je aplikace připravená k nasazení na uživatele nebo zákazníků, Visual Studio poskytuje nástroje k tomu, jestli nasazujete na Microsoft Store, na web služby SharePoint, nebo s technologiemi InstallShield nebo instalační služba systému Windows. Je přístupné pomocí rozhraní IDE. Další informace najdete v tématu [nasazení aplikací, služeb a komponent](../deployment/deploying-applications-services-and-components.md).

## <a name="quick-tour-of-the-ide"></a>Stručný přehled prostředí IDE

Následující obrázek ukazuje tak, abyste získali visual Přehled sady Visual Studio, Visual Studio s otevřít projekt spolu s několika okna klíče nástrojů, které budou s největší pravděpodobností používat:

- [Průzkumník řešení](../ide/solutions-and-projects-in-visual-studio.md) umožňuje zobrazit, přejděte a spravovat soubory s kódem. Průzkumník řešení pomáhá organizovat kód seskupením soubory do řešení a projekty.

- [Editor](../ide/writing-code-in-the-code-and-text-editor.md) okno, kde budete pravděpodobně tráví většinu doby, zobrazuje kódu a umožní vám upravit zdrojový kód a návrh uživatelského rozhraní.

- [Výstup](../ide/reference/output-window.md) je okno, kde Visual Studio odešle jeho oznámení, jako je ladění a chybové zprávy, upozornění kompilátoru, publikování stavové zprávy a další. Každý zdroj zpráva má vlastní kartě.

- [Team Explorer (VSTS)](/vsts/user-guide/work-team-explorer) slouží ke sledování pracovní položky a sdílet s ostatními kódu pomocí technologie pro řízení verzí, jako třeba [Git](https://git-scm.com/) a [Team Foundation verze ovládacího prvku (TFVC)](/vsts/tfvc/overview).

- [Cloud Explorer](/azure/vs-azure-tools-resources-managing-with-cloud-explorer) umožňuje zobrazení a správě prostředků Azure, jako je například virtuální počítače, tabulek, databází SQL a další. Pokud konkrétní operace vyžaduje, aby na portálu Azure, Průzkumník cloudu poskytuje odkazy, které vás zavedou na místě v portálu Azure, které budete muset přejít.

![Visual Studio IDE](../ide/media/visualstudioide.png)

Toto jsou některé další běžné funkce produktivitu v sadě Visual Studio:

- [Snadné spuštění](../ide/reference/quick-launch-environment-options-dialog-box.md) vyhledávacího pole je skvělým způsobem, jak rychle najít, co je třeba v sadě Visual Studio. Stačí spustit zadáním názvu ať hledáte a Visual Studio zobrazí výsledky, které dostanete přesně, kde chcete přejít. **Snadné spuštění** také ukazuje odkazy, které spustit instalační program Visual Studio pro všechny úlohy nebo jednotlivých součástí.

  ![Rychlé spuštění vyhledávacího pole](../ide/media/VSIDE_Tour_QuickLaunch.png)

- [Refaktoring](../ide/refactoring-in-visual-studio.md) zahrnuje operace, jako je inteligentního přejmenování proměnných Přesun vybrané řádky kódu do samostatné funkce, přesunutí kódu do jiných umístění, způsob parametry funkce a další.

 ![Refaktoring](../ide/media/VSIDE_refactor.png)

- **IntelliSense** je také souhrnný název pro sadu oblíbených funkcí, které zobrazují informace o typu o kódu přímo v editoru a v některých případech zápisu malých bits kódu pro vás. Je to jako mít základní dokumentace vložené v editoru ušetří práci s k vyhledání informací o typu v okně samostatné nápovědy. Funkce IntelliSense se liší podle jazyka. Další informace najdete v tématu [C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ IntelliSense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md), a [jazyka Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md). Některé funkce IntelliSense v práci na následujícím obrázku:

  ![Seznam členů v sadě Visual Studio](../ide/media/vs2017_Intellisense.png)

- **Podtržení vlnovkou** jsou podtržení vlnovkami red, které vás upozorní na chyby nebo potenciální problémy ve vašem kódu v reálném čase během psaní. To umožňuje opravit okamžitě bez čekání na chyby zjištěné při kompilaci nebo čas spuštění. Pokud je ukazatel myši nad vlnovka, zobrazí další informace o této chybě. Žárovky může zobrazit i na levém okraji s návrhy, jak chybu opravit. Další informace najdete v tématu [rychlé akce](../ide/quick-actions.md).

 ![Podtržení vlnovkou](../ide/media/vs2017_squiggle.png)

- [Hierarchie volání](../ide/reference/call-hierarchy.md) okno můžete otevřít v místní nabídce textového editoru zobrazíte metody, které volání a jsou volány, metoda pod pomocí kurzoru (bod vložení).

 ![Hierarchie volání – okno](../ide/media/VSIDE_call_hierarchy.png)

- [Codelensu](../ide/find-code-changes-and-other-history-with-codelens.md) umožňuje najít odkazy a změny provedené v kódu, propojené chyby, pracovní položky, kód recenze a testování částí všechny bez opuštění editoru.

 ![Codelensu](../ide/media/codelensoverview.png)

- [Funkce Náhled definice](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) v okně se zobrazí vložené definice metoda nebo typ bez nutnosti opustit váš aktuální kontext.

 ![Funkce Náhled definice](../ide/media/VSIDE_peek_definition.png)

- **Přejít k definici** možnost místní nabídky přejdete přímo na místě, kde je definována funkce nebo objektu. Další příkazy navigace jsou k dispozici také kliknutím pravým tlačítkem myši v editoru.

 ![Přechod na definici](../ide/media/VSIDE_go_to_definition.png)

## <a name="manage-your-source-code-and-collaborate-with-others"></a>Správa zdrojového kódu a spolupracovat s ostatními

Můžete spravovat vašeho zdrojového kódu v hostované všechny zprostředkovatele, včetně Githubu úložiště Git. Nebo použijte [Visual Studio Team Services (VSTS)](/vsts/index) ke správě kód společně se chyby a pracovní položky pro celý projekt. V tématu [začít pracovat s Git a Team Services (služby VSTS)](/vsts/git/gitquickstart?tabs=visual-studio) Další informace o správě úložiště Git v sadě Visual Studio pomocí Team Explorer. Visual Studio má také další funkce integrované zdroj ovládacího prvku. Další informace o nich najdete v tématu [Git nové funkce v aplikaci Visual Studio 2017 (blog)](https://blogs.msdn.microsoft.com/visualstudioalm/2017/03/06/new-git-features-in-visual-studio-2017/).

Visual Studio Team Services je Cloudová služba pro hostování projektů softwaru a povolení spolupráce v týmy. Služby VSTS podporuje systémy Git a Team Foundation zdrojového kódu, jakož i metodiky Scrum a Agile a CMMI vývoj. Team Foundation verze ovládacího prvku (TFVC) používá jedinou, centralizovanou server úložiště ke sledování a verze souborů. Místní změny jsou vždy změnami na centrálním serveru, kde můžete jinými vývojáři získání nejnovějších změn.

Team Foundation Server (TFS) je Centrum správy životního cyklu aplikace Visual Studio. Umožňuje everyone spojené s procesu vývoje se zúčastnit pomocí jednoho řešení. TFS je užitečné pro správu heterogenní týmy a projekty, příliš.

Pokud máte účet Visual Studio Team Services nebo Team Foundation Server v síti, můžete se připojit k němu prostřednictvím **Team Explorer** oken v sadě Visual Studio. Z tohoto okna můžete zkontrolovat kód do nebo z zdrojového kódu, správě pracovních položek, sestavení a spuštění přístup týmové místnosti a pracovní prostory. Můžete otevřít **Team Explorer** z **Snadné spuštění** pole, nebo v hlavní nabídce z **zobrazení** > **Team Explorer** nebo z **Team** > **Správa připojení**.

Na následujícím obrázku **Team Explorer** okna pro řešení, který je hostován v služby VSTS.

![Visual Studio Team Explorer](../ide/media/vs2017_teamexplorer.png)

Můžete také automatizovat vašeho procesu sestavení vytvářet kód, který jste zkontrolovali devs ve vašem týmu do správy verzí. Lze například sestavit jeden nebo více projektů v noci nebo pokaždé, když je kód vrácen se změnami. Další informace najdete v tématu [sestavení a verze (služby VSTS a sady TFS)](/vsts/build-release/index).

## <a name="connect-to-services-databases-and-cloud-based-resources"></a>Připojení ke službám, databází a cloudové prostředky

Cloud je velmi důležitá pro dnešní online world a Visual Studio poskytuje způsob, jak využít. Například funkce připojené Services umožňuje připojení aplikace ke službám. Aplikace můžete ukládat data na úložiště Azure, mimo jiné.

![Připojených služeb](../ide/media/VSIDE_Tour_Connected_Services.png)

Výběr služby na **připojené služby** stránka spustí **připojené služby** spuštění průvodce, který nakonfiguruje projektu a stahuje potřebné balíčky NuGet, které vám pomůžou kódování proti Služba.

Můžete zobrazit a spravovat prostředky na základě Azure cloud v sadě Visual Studio pomocí [Průzkumník cloudu](/azure/vs-azure-tools-resources-managing-with-cloud-explorer). Průzkumník cloudu zobrazuje všechny účty, které jsou spravované v rámci předplatného Azure, ke kterému jste přihlášeni do prostředků Azure. Můžete získat **Průzkumník cloudu** výběrem **Azure development** zatížení v instalačním programu sady Visual Studio.

![Průzkumník cloudu](../ide/media/VSIDE_CloudExplorer.png)

**V Průzkumníku serveru** vám pomůže Procházet a spravovat instance systému SQL Server a prostředky místně, vzdáleně a na Azure, Salesforce.com, Office 365 a weby. Chcete-li otevřít **Průzkumníka serveru**, v hlavní nabídce zvolte **zobrazení** > **Průzkumníka serveru**. V tématu [přidat nová připojení](../data-tools/add-new-connections.md) pro další informace o použití Průzkumníka serveru.

[SQL Server Data Tools (SSDT)](/sql/ssdt/download-sql-server-data-tools-ssdt) je výkonný vývojové prostředí pro SQL Server, databáze SQL Azure a Azure SQL Data Warehouse. Umožňuje vytvářet, ladit, udržovat a Refaktorovat databáze. Můžete pracovat s projektem databáze, nebo přímo s připojené databáze instance nebo vypnout místně.

**Průzkumník objektů systému SQL Server** v sadě Visual Studio poskytuje zobrazení objektů databáze podobně jako SQL Server Management Studio. Průzkumník objektů systému SQL Server můžete pro účely správy a návrh lehká databáze, včetně úpravy dat v tabulce, porovnání schémat, provádění dotazů pomocí kontextové nabídky přímo z Průzkumníka objektů systému SQL Server a další.

![Průzkumník objektů systému SQL Server](../ide/media/vs2015_sqlobjectexplorer.png)

## <a name="extend-visual-studio"></a>Rozšíření sady Visual Studio

Pokud Visual Studio nemá přesný funkce, které potřebujete, můžete ho přidat! Přizpůsobení integrovaného vývojového prostředí na základě vašeho pracovního postupu a styl, přidat podporu pro externí nástroje ještě integrované pomocí sady Visual Studio a upravit stávající funkce zvyšuje produktivitu. Nejnovější verzi Visual Studio Extensibility Tools (VS SDK), najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Kompilátoru platformu .NET ("Roslyn") můžete použít k zápisu vlastní analyzátorů kódu a generátory kódu. Najít všechno, co potřebujete v [Roslyn](https://github.com/dotnet/Roslyn).

Najít [existující rozšíření](https://marketplace.visualstudio.com/vs) pro sadu Visual Studio vytvořené vývojáři Microsoftu a také naše komunita vývoj.

Další informace o rozšíření sady Visual Studio najdete v tématu [rozšíření Visual Studio IDE](https://www.visualstudio.com/vs/extend/).

## <a name="learn-more-and-find-out-whats-new"></a>Další informace a zjistit, co je nového

Pokud jste Visual Studio před nepoužívali, podívejte se na [začít s vývojem pomocí sady Visual Studio](../ide/get-started-developing-with-visual-studio.md), nebo se podívejte se na bezplatné sady Visual Studio kurzy k dispozici na [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033). Pokud chcete rezervovat nových funkcí v Visual Studio 2017, najdete v části [co je nového ve Visual Studio 2017](../ide/whats-new-in-visual-studio.md).

Blahopřejeme k dokončení prohlídku Visual Studio IDE! Věříme, že jste se dozvěděli, něco užitečné informace o některých jeho hlavní funkce.

## <a name="see-also"></a>Viz také

* [Integrované vývojové prostředí sady Visual Studio](https://www.visualstudio.com/vs/)
* [Soubory ke stažení sady Visual Studio](https://www.visualstudio.com/downloads/)
* [Blog Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/)
* [Fóra Visual Studio](https://social.msdn.microsoft.com/Forums/vstudio/home?category=visualstudio%2Cvsarch%2Cvsdbg%2Cvstest%2Cvstfs%2Cvsdata%2Cvsappdev%2Cvisualbasic%2Cvisualcsharp%2Cvisualc)
* [Microsoft Virtual Academy](https://mva.microsoft.com/)