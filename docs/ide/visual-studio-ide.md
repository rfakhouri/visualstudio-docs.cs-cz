---
title: "Přehled sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2017
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5bde32fc86610fa451aa01659401362fe4207f5c
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
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

[Application Insights](https://marketplace.visualstudio.com/items?itemName=VisualStudioOnlineApplicationInsights.application-insights) pomáhá rozpoznat a diagnostikovat problémy kvality ve svých aplikacích a webové služby. Application Insights také vám pomůže pochopit, co uživatelé ve skutečnosti provádějí s vaší aplikací, můžete optimalizovat uživatelské prostředí.

### <a name="create-apps-for-the-web"></a>Vytvoření aplikace pro web

Web jednotky naše moderní world a Visual Studio můžete usnadňuje psaní aplikací pro ni. Můžete vytvořit webové aplikace pomocí ASP.NET, Node.js, Python, JavaScript a TypeScript. Visual Studio rozumí webové platformy jako úhlová, jQuery, Express a další. Spuštěné na operačních systémech Windows, Mac a Linux .NET Core a ASP.NET Core. [ASP.NET Core](http://www.asp.net/core/overview) je hlavní aktualizace MVC, WebAPI a SignalR a běží na systému Windows, Mac a Linux.  ASP.NET Core má byly navrženy od základů až zajistit, že jste s .NET Štíhlá a bez možnosti složení zásobníku pro vytváření webových moderní cloudové aplikace a služby.

Další informace najdete v tématu [moderních webových nástrojů](https://www.visualstudio.com/vs/modern-web-tooling/).

### <a name="build-cross-platform-apps-and-games"></a>Vytváření aplikací pro různé platformy a hry

Visual Studio můžete použít k sestavení aplikací a her pro Android, iOS, Linux, Windows a dalších zařízení. Další informace naleznete na [vývoj mobilních řešení pro různé platformy](../cross-platform/cross-platform-mobile-development-in-visual-studio.md). Universal Windows Apps můžete využít kódu napříč různými platformami. V tématu [univerzálních aplikací pro Windows](https://dev.windows.com/windows-apps) Další informace.

Zvolte nástroje, které je třeba na základě požadavků na aplikace a jazyk, který chcete použít:

- [Xamarin pro Visual Studio](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md): běžné kód základní v jazyce C# pro všechna zařízení.

- [Nástroje sady Visual Studio pro Apache Cordova](../cross-platform/visual-studio-tools-for-apache-cordova.md): běžné kód základní pro HTML, CSS a JavaScript a Typescript.

- [Visual Studio Tools for Unity](../cross-platform/visual-studio-tools-for-unity.md): vývoj her pro vytváření 2D/3D v jazyce C#.

- [C++ pro vývoj pro různé platformy](../cross-platform/visual-cpp-for-cross-platform-mobile-development.md): sdílené knihovny kódu a aplikace v jazyce C++.

- [Visual Studio Emulator for Android](../cross-platform/visual-studio-emulator-for-android.md): Visual Studio Emulator for Android: ladit a testovat aplikace pro Android bez ohledu na to rozhraní IDE.

[Vytvoření hry s použitím sady Visual Studio](https://www.visualstudio.com/vs/game-development/) nástroje pro vývoj her například DirectX, Unity, nerealiz, Kokosové a další.

Visual Studio, můžete to udělat celou řadu věcí další pomoc. Získat úplný seznam najdete v tématu [Visual Studio IDE](https://www.visualstudio.com/vs/).

## <a name="install-the-visual-studio-ide"></a>Instalace sady Visual Studio IDE

Pokud chcete začít, stáhněte si Visual Studio a nainstalujte ho do systému. Tuto součást můžete stáhnout na [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

Visual Studio je nyní jednodušší než kdy dřív! Modulární instalační program vám umožňuje vybrat a nainstalovat *úlohy*, což jsou skupiny součástí, které jsou potřebné pro programovací jazyk nebo platformu dáváte přednost. Tato strategie pomáhá udržovat nároků instalace Visual Studia, která je menší než kdy dřív, což znamená, nainstaluje se a aktualizuje rychlejší příliš.

Postupujte podle kroků pro vytvoření programu níže, nezapomeňte vyberte a nainstalujte **Universal Windows Platform Development** zatížení.

![Instalační program Visual Studio](../ide/media/vside_tour_install_dialog.png)

Kromě instalace lepší výkon má Visual Studio 2017 také kratší spuštění IDE a načíst dobu řešení.

Další informace o nastavení v systému Visual Studia, najdete v části [nainstalovat Visual Studio 2017](../install/install-visual-studio.md).

## <a name="sign-in"></a>Přihlásit se

Při prvním spuštění sady Visual Studio, můžete volitelně Přihlaste se pomocí účtu Microsoft nebo váš pracovní nebo školní účet. Probíhá přihlašování umožňuje synchronizovat nastavení sady Visual Studio, například rozložení oken v různých zařízeních. Je také propojení automaticky ke službám, které byste měli, jako je například předplatných Azure a Visual Studio Team Services.

## <a name="create-a-program"></a>Vytvořit program

Další informace o něco jeden vhodný způsob je pro použití! Umožňuje podrobné informace a vytvořit nové, jednoduchý program.

1. Otevřete Visual Studio. V nabídce zvolte **soubor** > **nový** > **projektu**.

  ![snímek obrazovky](../ide/media/VSIDE_Tour_NewProject1.png)

  Alternativně můžete vytvořit nový projekt pomocí stránce Start. Další informace najdete v tématu [plně využívat přepracovali stránce Start (blog)](https://blogs.msdn.microsoft.com/visualstudio/2016/11/29/harness-the-power-of-the-redesigned-start-page/).

1. **Nový projekt** dialogové okno zobrazí několik šablon projektu. Vyberte **univerzální pro Windows** kategorii v **Visual C#**, vyberte **prázdná aplikace (univerzální pro Windows)** šablony a potom vyberte **OK**tlačítko.

  > [!NOTE]
  > Pokud nevidíte **univerzální pro Windows** kategorie, je třeba nainstalovat **Universal Windows Platform Development** zatížení. To pokud chcete udělat, vyberte **otevřete instalační program Visual Studio** odkaz na spodní levé straně **nový projekt** dialogové okno. Po **instalační program Visual Studio** otevře, vyberte **Universal Windows Platform Development** zatížení a potom zvolte **upravit**.

  ![Šablonu prázdná aplikace UWP](../ide/media/new-uwp-blank-app-template.png)

  Tím se vytvoří nový prázdný Universal Windows aplikace projekt pomocí jazyka C# a XAML jako programovací jazyky. Počkejte chvilku při Visual Studio nastaví projekt pro vás. Pokud se zobrazí výzva k zadání informací, přijměte výchozí hodnoty právě teď.

1. V **nový projekt univerzální platformu Windows** dialogové okno pole, přijměte výchozí hodnoty tak, že zvolíte **OK**.

1. Zanedlouho byste měli vidět něco podobného jako na následujícím snímku obrazovky. Soubory projektu jsou uvedeny na pravé straně v okně nazývá Průzkumník řešení.

  ![snímek obrazovky](../ide/media/VSIDE_Tour_NewProject3.png)

1. V Průzkumníku řešení, zvolte málo černý trojúhelník vedle MainPage.xaml soubor rozbalte ho a měli byste vidět souboru MainPage.xaml.cs pod. Vyberte tento soubor (který obsahuje kód C#) a ten se otevře.

  Kód jazyka C# v MainPage.xaml.cs se zobrazí v editoru kódu na levé straně obrazovky. Všimněte si, že syntaxe kódu je automaticky obarvené udávajících různé typy kódu, například příkazy nebo komentáře. Kromě toho malé, svislá přerušované čáry v kódu označují, které složené závorky odpovídat navzájem a čísla řádků vám pomohou vyhledat kód později. Můžete použít znaky minus malé, zabalené sbalit nebo rozbalte kódu. Tento kód osnovy funkce umožňuje skrýt kódu, které nepotřebujete, pomáhá minimalizovat zbytečné soubory na obrazovce.

  ![](../ide/media/VSIDE_Tour_NewProject3a.png)

  Existují jiné nabídky a nástroje systému windows k dispozici, ale umožňuje přesun chvíli.

1. Přidání tlačítka do formuláře XAML uživatelům způsob, jak pracovat s vaší aplikací. Chcete-li to provést, otevřete soubor MainPage.xaml. Zobrazí se zobrazení rozdělení: designer výše, pro vizuální umístění ovládacích prvků a zobrazení kódu níže, který ukazuje kódu návrháře XAML. Když spustíte program později, co se zobrazí v návrháři se změní na okno, které uživatelé uvidí, "formulář", a základní XAML Určuje, co se zobrazí na formuláři.

1. Na levé straně obrazovky vyberte **sada nástrojů** otevřete sady nástrojů. Sada nástrojů obsahuje řadu visual ovládacích prvků, které můžete přidat do formulářů. Prozatím se právě přidáme ovládacího prvku tlačítko.

1. Rozbalte **běžné ovládací prvky XAML** části a pak přetáhněte ovládacího prvku tlačítka se o středu tvaru. (Přesné umístění není důležité.)

  ![snímek obrazovky](../ide/media/VSIDE_Tour_Toolbox.png)

  Když jste hotovi, měli vidět něco podobného jako následující.

  ![snímek obrazovky](../ide/media/VSIDE_Tour_XAMLButton.png)

  Tlačítko je v designeru jeho základní kódu (zvýrazněné) se automaticky přidá do kódu návrháři XAML

1. Umožňuje změnit některé kódu XAML. Přejmenujte text v kódu tlačítko z `Button` k `Hello!`.

  ![snímek obrazovky](../ide/media/VSIDE_Tour_XAMLButton2.png)

1. Nyní spusťte aplikaci. To provedete tak, že zvolíte **spustit** (![tlačítko Start](../ide/media/VSIDE_StartButton.png)) tlačítka na panelu nástrojů nebo výběrem **F5** klíče, nebo v nabídce, výběrem možnosti **ladění**  >  **Spustit ladění**.

  ![snímek obrazovky](../ide/media/VSIDE_Tour_RunButton.png)

  Aplikace začne jeho procesu sestavení a stavové zprávy se zobrazují v okně výstupu. Brzy měli byste vidět formuláře se vaše tlačítko se objeví. Nyní máte spuštěné aplikaci!

  ![snímek obrazovky](../ide/media/VSIDE_Tour_RunProject.png)

  Samozřejmě neprovádí mnohem nyní, ale můžete přidat další funkce k němu později podle potřeby.

1. Po dokončení spuštění programu, zvolte Stop (![Tlačítko Zastavit](../ide/media/VSIDE_StopButton.png)) tlačítka na panelu nástrojů zastavte ji.

Pojďme recap, co jste zatím: vytvoření nového projektu C# univerzální pro Windows v sadě Visual Studio, zobrazit jeho kód, přidání ovládacího prvku do návrháře, změnit některé kódu XAML a pak se spustil projekt. I když v tomto příkladu je zjednodušená proces, to ukazuje některé běžné části Visual Studio IDE, který budete používat při vývoji své vlastní aplikace. Pokud chcete další informace o tomto příkladu, najdete v části [vytvořit "Hello, world" aplikace (XAML)](/windows/uwp/get-started/create-a-hello-world-app-xaml-universal).

## <a name="debug-test-and-improve-your-code"></a>Ladění, testování a zlepšit váš kód

Nic spustí perfektně vždy. Při psaní kódu, budete muset spustit a otestovat ho chyb a výkonu. Visual Studio špičkových ladění systému umožňuje ladit kód spuštěný ve vašem místním projektu, na vzdáleném zařízení nebo na emulátoru jako jsou ty pro zařízení Android nebo Windows Phone. Můžete krok prostřednictvím kódu jeden příkaz v čase a zkontrolovat proměnné, jak můžete přejít, můžete krokovat vícevláknové aplikace a můžete nastavit zarážky, které jsou pouze dosáhl při splnění zadané podmínky. Můžete sledovat hodnoty proměnných, jako je kód spuštěn a další. Všechny tyto se dají spravovat editoru kódu, samostatně, takže nemusíte opustit váš kód.

![Ladění](../ide/media/VSIDE_Tour_Debugging.png)

Pro testování, Visual Studio nabízí testování, IntelliTest, zátěže a testování výkonu a další jednotky. Chcete-li získat další informace o ladění proces sady Visual Studio, najdete v části [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md). Další informace o testování najdete v tématu [scénáře a testovacích nástrojů](../test/developer-testing-scenarios.md). Další informace o zvýšení výkonu aplikací, najdete v části [profilace prohlídka funkce](../profiling/profiling-feature-tour.md).

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

- [Snadné spuštění](../ide/reference/quick-launch-environment-options-dialog-box.md) vyhledávacího pole je skvělým způsobem, jak rychle najít, co je třeba v sadě Visual Studio. Stačí spustit zadáním názvu ať hledáte a Visual Studio zobrazí výsledky, které dostanete přesně, kde chcete přejít. Snadné spuštění také ukazuje odkazy, které spustit instalační program Visual Studio pro všechny úlohy nebo jednotlivých součástí.

  ![Rychlé spuštění vyhledávacího pole](../ide/media/VSIDE_Tour_QuickLaunch.png)

- [Refaktoring](../ide/refactoring-in-visual-studio.md) zahrnuje operace, jako je inteligentního přejmenování proměnných Přesun vybrané řádky kódu do samostatné funkce, přesunutí kódu do jiných umístění, způsob parametry funkce a další.

 ![Refaktoring](../ide/media/VSIDE_refactor.png)

- **IntelliSense** je také souhrnný název pro sadu oblíbených funkcí, které zobrazují informace o typu o kódu přímo v editoru a v některých případech zápisu malých bits kódu pro vás. Je to jako mít základní dokumentace vložené v editoru ušetří práci s k vyhledání informací o typu v okně samostatné nápovědy. Funkce IntelliSense se liší podle jazyka. Další informace najdete v tématu [C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ Intellisense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md), a [specifické pro Visual Basic IntelliSense ](../ide/visual-basic-specific-intellisense.md). Některé funkce IntelliSense v práci na následujícím obrázku:

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

- Nástroj související [Prohlížeč objektů](http://msdn.microsoft.com/f89acfc5-1152-413d-9f56-3dc16e3f0470), umožní vám prohlédnout sestavení .NET nebo prostředí Windows Runtime v systému, které chcete zjistit, jaká se typy obsahuje a obsahuje tyto typy jaké členy (vlastnosti, metody, události atd.).

  ![Prohlížeč objektů zobrazující objekt System.Timer](../ide/media/objectbrowser.png)

## <a name="manage-your-source-code-and-collaborate-with-others"></a>Správa zdrojového kódu a spolupracovat s ostatními

Můžete spravovat vašeho zdrojového kódu v hostované všechny zprostředkovatele, včetně Githubu úložiště Git. Nebo použijte [Visual Studio Team Services (VSTS)](/vsts/index) ke správě kód společně se chyby a pracovní položky pro celý projekt. V tématu [začít pracovat s Git a Team Services (služby VSTS)](/vsts/git/gitquickstart?tabs=visual-studio) Další informace o správě úložiště Git v sadě Visual Studio pomocí Team Explorer. Visual Studio má také další funkce integrované zdroj ovládacího prvku. Další informace o nich najdete v tématu [nové funkce Git v nástroji Visual Studio 2017 (blog)](https://blogs.msdn.microsoft.com/visualstudioalm/2017/03/06/new-git-features-in-visual-studio-2017/).

Visual Studio Team Services je Cloudová služba pro hostování projektů softwaru a povolení spolupráce v týmy. Služby VSTS podporuje systémy Git a Team Foundation zdrojového kódu, jakož i metodiky Scrum a Agile a CMMI vývoj. Team Foundation verze ovládacího prvku (TFVC) používá jedinou, centralizovanou server úložiště ke sledování a verze souborů. Místní změny jsou vždy změnami na centrálním serveru, kde můžete jinými vývojáři získání nejnovějších změn.

Team Foundation Server (TFS) je Centrum správy životního cyklu aplikace Visual Studio. Umožňuje everyone spojené s procesu vývoje se zúčastnit pomocí jednoho řešení. TFS je užitečné pro správu heterogenní týmy a projekty, příliš.

Pokud máte účet Visual Studio Team Services nebo Team Foundation Server v síti, připojujete se k němu pomocí okna Průzkumník týmových projektů v sadě Visual Studio. Z tohoto okna můžete zkontrolovat kód do nebo z zdrojového kódu, správě pracovních položek, sestavení a spuštění přístup týmové místnosti a pracovní prostory. Můžete otevřít Průzkumník týmových projektů z **Snadné spuštění** pole, nebo v hlavní nabídce z **zobrazení, Team Explorer** nebo z **tým, Správa připojení**.

Následující obrázek ukazuje okno Průzkumník týmových projektů pro řešení, který je hostován v služby VSTS.

![Visual Studio Team Explorer](../ide/media/vs2017_teamexplorer.png)

Můžete také automatizovat vašeho procesu sestavení vytvářet kód, který jste zkontrolovali devs ve vašem týmu do správy verzí. Lze například sestavit jeden nebo více projektů v noci nebo pokaždé, když je kód vrácen se změnami. V tématu [sestavení a verze (služby VSTS a sady TFS)](/vsts/build-release/index) Další informace.

## <a name="connect-to-services-databases-and-cloud-based-resources"></a>Připojení ke službám, databází a cloudové prostředky

Cloud je velmi důležitá pro dnešní online world a Visual Studio poskytuje způsob, jak využít. Například funkce připojené Services umožňuje připojení aplikace ke službám. Aplikace můžete ukládat data na úložiště Azure, mimo jiné.

![Připojených služeb](../ide/media/VSIDE_Tour_Connected_Services.png)

Výběr služby na **připojené služby** spustí Průvodce připojené služby, který nakonfiguruje projektu a stahování nezbytných balíčků NuGet, které vám pomůžou spuštění kódování pro službu.

Můžete zobrazit a spravovat prostředky na základě Azure cloud v sadě Visual Studio pomocí [Průzkumník cloudu](/azure/vs-azure-tools-resources-managing-with-cloud-explorer). Průzkumník cloudu zobrazuje všechny účty, které jsou spravované v rámci předplatného Azure, ke kterému jste přihlášeni do prostředků Azure. Průzkumník cloudu můžete získat tak, že vyberete **Azure development** zatížení v instalačním programu sady Visual Studio.

![Průzkumník cloudu](../ide/media/VSIDE_CloudExplorer.png)

**V Průzkumníku serveru** vám pomůže Procházet a spravovat instance systému SQL Server a prostředky místně, vzdáleně a na Azure, Salesforce.com, Office 365 a weby. Chcete-li otevřít Průzkumníka serveru na hlavní nabídky, zvolte **zobrazení** > **Průzkumníka serveru**. V tématu [přidat nová připojení](../data-tools/add-new-connections.md) pro další informace o použití Průzkumníka serveru.

[SQL Server Data Tools (SSDT)](/sql/ssdt/download-sql-server-data-tools-ssdt) je výkonný vývojové prostředí pro SQL Server, databáze SQL Azure a Azure SQL Data Warehouse. Umožňuje vytvářet, ladit, udržovat a Refaktorovat databáze. Můžete pracovat s projektem databáze, nebo přímo s připojené databáze instance nebo vypnout místně.

**Průzkumník objektů systému SQL Server** v sadě Visual Studio poskytuje zobrazení objektů databáze podobně jako SQL Server Management Studio. Průzkumník objektů systému SQL Server můžete pro účely správy a návrh lehká databáze, včetně úpravy dat v tabulce, porovnání schémat, provádění dotazů pomocí kontextové nabídky přímo z Průzkumníka objektů systému SQL Server a další.

![SQL Server Object Explorer](../ide/media/vs2015_sqlobjectexplorer.png)

## <a name="extend-visual-studio"></a>Rozšíření sady Visual Studio

Pokud Visual Studio nemá přesný funkce, které potřebujete, můžete ho přidat! Přizpůsobení integrovaného vývojového prostředí na základě vašeho pracovního postupu a styl, přidat podporu pro externí nástroje ještě integrované pomocí sady Visual Studio a upravit stávající funkce zvyšuje produktivitu. Nejnovější verzi Visual Studio Extensibility Tools (VS SDK), najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Kompilátoru platformu .NET (Roslyn) můžete použít k zápisu vlastní analyzátorů kódu a generátory kódu. Najít všechno, co potřebujete v [Roslyn](https://github.com/dotnet/Roslyn).

Najít [existující rozšíření](https://marketplace.visualstudio.com/vs) pro sadu Visual Studio vytvořené vývojáři Microsoftu a také naše komunita vývoj.

Další informace o rozšíření sady Visual Studio najdete v tématu [rozšíření Visual Studio IDE](https://www.visualstudio.com/vs/extend/).

## <a name="learn-more-and-find-out-whats-new"></a>Další informace a zjistit, co je nového

Pokud jste Visual Studio před nepoužívali, podívejte se na [získat spuštění vývoj pomocí sady Visual Studio](../ide/get-started-developing-with-visual-studio.md), nebo se podívejte se na bezplatné sady Visual Studio kurzy k dispozici na [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033). Pokud chcete rezervovat nových funkcí v Visual Studio 2017, najdete v části [co je nového ve Visual Studio 2017](../ide/whats-new-in-visual-studio.md).

Blahopřejeme k dokončení prohlídku Visual Studio IDE! Věříme, že jste se dozvěděli, něco užitečné informace o některých jeho hlavní funkce.

## <a name="see-also"></a>Viz také

* [Integrované vývojové prostředí sady Visual Studio](https://www.visualstudio.com/vs/)
* [Stažení sady Visual Studio](https://www.visualstudio.com/downloads/)
* [Blog sady Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/)
* [Visual Studio Forums](https://social.msdn.microsoft.com/Forums/vstudio/home?category=visualstudio%2Cvsarch%2Cvsdbg%2Cvstest%2Cvstfs%2Cvsdata%2Cvsappdev%2Cvisualbasic%2Cvisualcsharp%2Cvisualc)
* [Microsoft Virtual Academy](https://mva.microsoft.com/)
* [Channel 9](https://channel9.msdn.com/)