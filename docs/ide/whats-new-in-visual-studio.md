---
title: Co je nového ve Visual Studio 2017
description: Další informace o nových funkcích ve Visual Studio 2017.
ms.custom: ''
ms.date: 05/09/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
f1_keywords:
- VS.StartPage.WhatsNew
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 7307e180-ba28-4774-8a43-cbb980085a71
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 542814c5902f2dba1c76b33f78273aadfb583eff
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282970"
---
# <a name="what39s-new-in-visual-studio-2017"></a>Co&#39;s nového ve Visual Studio 2017

**Aktualizováno pro [15.7 verze](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default)**

Hledáte upgrade z předchozí verze sady Visual Studio? Tady je co Visual Studio 2017 nabízejí jste: bezkonkurenční produktivitu pro všechny vývojáře, všechny aplikace a libovolnou platformu. Použijte Visual Studio 2017 k vývoji aplikací pro Android, iOS, Windows, Linux, web a cloud. Svůj kód můžete rychle psát, snadno ladit a diagnostikovat, často testovat a bez obav vydávat. Navíc si můžete sadu Visual Studio rozšířit a přizpůsobit pomocí svých vlastních rozšíření. Použití správy verzí, být agilní a efektivně spolupracovat s touto verzí!

Zde je podrobný rekapitulace změny, které byly provedeny od předchozích verzí sady Visual Studio 2015:

* **[Předefinovat Základy](#redefined-fundamentals)**. Nové prostředí instalace znamená, že můžete nainstalovat rychleji a nainstalovat, co má v případě potřeby. Jestli chcete načíst velkých řešení a projektů nebo pracovat na složky kódu nebo i na jeden soubor kódu, Visual Studio rychleji spustí. A Visual Studio umožňuje soustředit na velký obrázek, zejména pro týmy osvojují DevOps.
* **[Výkon a produktivitu](#performance-and-productivity)**. Jsme se zaměřili na nové a moderní mobilní, cloudové a možnosti vývoj aplikací. Vylepšili jsme také celkový akvizice, výkon, a vyskytne obecné produktivity. Visual Studio rychleji spustí, je rychlejší reakce a vyžaduje méně paměti než před.
* **[Vývoj aplikací s Azure Cloud](#cloud-app-development-with-azure)**. Předdefinované sada nástroje Azure umožňují snadno vytvářet první cloudové aplikace používá technologii Microsoft Azure. Visual Studio snadno ke konfiguraci, vytvářet, ladit, balíčku a nasazovat aplikace a služby v Azure.
* **[Vývoj aplikací pro Windows](#windows-app-development)**. Použití šablon UWP v Visual Studio 2017 k vytvoření jedné projektu pro všechna zařízení s Windows 10 &ndash; počítač, tablet, phone, Xbox, HoloLens, Surface Hub a další. Poté vytvoří balíček aplikace a odešlete ji do Microsoft Store z Visual Studia schválení vaší aplikace zákazníkům.
* **[Vývoj mobilních aplikací](#mobile-app-development)**. V aplikaci Visual Studio 2017 můžete inovacemi. Zajistěte a získat výsledky rychlá a má Xamarin, který kombinuje požadavků mobilních platforem pomocí jednoho jádra codebase a sadu znalostí. Přejděte mobilních s vaší stávající týmy, investice do technologie a kódu jazyka C# k poskytování příjemce úrovni prostředí plánem a v části nároky. Urychlit každý krok mobilní životního cyklu k poskytování špičkových příjemce prostředí nebo portfoliu kancelářské aplikace na základě kterých pracovníky.
* **[Vývoj pro různé platformy](#cross-platform-development)**. Bezproblémově poskytovat software na všechny cílové platformy. Rozšíření do systému SQL Server pomocí nástrojů Data Redgate DevOps procesy a bezpečně automatizovat nasazení databáze ze sady Visual Studio. Nebo použijte .NET Core pro zápis aplikace a knihovny, které běží ve Windows, Linux a operační systémy systému macOS beze změny. (A **nové v 15.3**: získat vedle sebe podporu pro rozhraní .NET Core 2.0 sady SDK.)
* **[Hry vývoj](#games-development)**. Pomocí nástrojů Visual Studio pro Unity (VSTU) můžete použít Visual Studio psaní herní a editor skriptů v jazyce C# a pak použijte jeho výkonný ladicí program k vyhledání a opravte chyby. Nejnovější verze VSTU zahrnuje pro Unity na ShaderLab shaderu jazyka, lepší vizualizace ladicího programu a generování kódu vylepšené pro Průvodce MonoBehavior zvýrazňování syntaxe. VSTU přináší také soubory projektu Unity, zprávy konzoly a možnost spuštění vaše hra do sady Visual Studio, takže může trávit méně času přepnutí do a z editoru Unity při psaní kódu.
* **[Vývoj pro AI](#ai-development)**. Pomocí nástrojů Visual Studio pro AI (**nové v 15,5**), funkce produktivitu sady Visual Studio můžete použít k urychlení AI inovace. Vytvoření, testování a nasazení hloubkové Learning / AI řešení, která bezproblémově integrovat s Azure Machine Learning robustní experimentování funkce, například odeslání dat přípravy a úlohy školení modelu transparentně pro různé výpočetní cíle. Visual Studio Tools for AI poskytuje podporu pro vlastní metriky a sledování historie spustit, což umožňuje reprodukovatelnosti datové vědy a auditování.

> [!NOTE]
> Úplný seznam nových funkcí a funkcí v Visual Studio 2017, najdete v článku [poznámky k verzi aktuální](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default). A funkce Náhled na budoucí funkce nabídek, najdete v článku [poznámky k verzi Preview](/visualstudio/releasenotes/vs2017-preview-relnotes?context=visualstudio/default).

Zde uvádíme podrobnější informace o některých nejdůležitějším vylepšení a nové funkce v nástroji Visual Studio 2017.

## <a name="redefined-fundamentals"></a>Předefinovaná základy

### <a name="a-new-setup-experience"></a>Nové prostředí pro instalaci

[Stáhněte si Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) nebo [požadavky na systém zkontrolujte Visual Studio](/visualstudio/productinfo/vs2017-system-requirements-vs?context=visualstudio/default)

 Visual Studio je snadnější a rychlejší instalaci jenom funkce, které budete potřebovat, pokud je potřebujete. A odinstaluje řádně, příliš.

 Nejdůležitější změnu a Všimněte si při instalaci sady Visual Studio je jeho nové instalace prostředí. Na **úlohy** kartě uvidíte možnosti instalace, které jsou seskupeny představují společné architektury, jazyky a platformy. Vysvětluje všechno vývoj aplikací .NET do C++ vývoj aplikací pro Windows, Linux a iOS.

Vyberte úlohy, je třeba a změnit, pokud je potřeba.

 ![Visual Studio 2017 dialogové okno nastavení](../install/media/install-visual-studio-enterprise.png)

A máte k dispozici možnosti a systém doladit vaší instalace příliš:

* Chcete vybrat vlastní součásti místo použití úlohy? Vyberte **jednotlivých součástí** kartě z instalačního programu.
* Chcete nainstalovat jazykové sady bez nutnosti změnit možnost jazyk Windows? Vyberte **jazykové sady** kartě Instalační služby.
* **Novinka v 15.7**: Chcete změnit umístění kde Visual Studio nainstaluje? Vyberte **možnosti instalace** kartě Instalační služby.

Další informace o novém prostředí instalace, včetně podrobné pokyny, které vás provede procesem, najdete v článku [instalaci sady Visual Studio](../install/install-visual-studio.md) stránky.

### <a name="a-focus-on-accessibility"></a>Zaměřená na usnadnění přístupu

**Novinka v 15.3**, jsme provedli přes 1,700 cílové opravy zlepšit kompatibilitu mezi Visual Studio a technologie pro usnadnění, které používají mnoho zákazníků. Existují desítky scénářů, které jsou více kompatibilní s čtečky obrazovky, motivy vysoký kontrast a další technologie pro usnadnění než kdy dřív. Ladicí program, editor a prostředí mít příliš všechny gotten významná vylepšení.

Další informace najdete v tématu [vylepšení přístupnosti v Visual Studio 2017 verze 15.3](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) příspěvku na blogu.

## <a name="performance-and-productivity"></a>Výkon a produktivita

### <a name="sign-in-across-multiple-accounts"></a>Přihlaste se napříč více účtů

Zavedli jsme nové identity služby v sadě Visual Studio, které můžete sdílet mezi Průzkumník týmových projektů, nástroje Azure, publikování Microsoft Store a další uživatelské účty.

Abyste mohli zůstat přihlášeného déle příliš. Visual Studio nebude zeptá se přihlásit znovu každých 12 hodin. Další informace najdete v tématu [přihlášení méně Visual Studio vyzve](https://blogs.msdn.microsoft.com/visualstudio/2016/08/15/fewer-visual-studio-sign-in-prompts/) příspěvku na blogu.

### <a name="start-visual-studio-faster"></a>Rychlejší spuštění sady Visual Studio

Nové centrum výkonu Visual Studio můžete optimalizovat čas spuštění IDE. Výkon Center uvádí všechny rozšíření a okna nástrojů, které může zpomalit spuštění IDE. Můžete ho použít ke zlepšení výkonu spuštění tak, že určíte při spuštění rozšíření, nebo zda jsou otevřené při spuštění nástroje windows.

### <a name="faster-on-demand-loading-of-extensions"></a>Rychlejší načítání na vyžádání rozšíření

Visual Studio je přesunutí jeho rozšíření (a práci s rozšíření jiných výrobců příliš) tak, aby se zatížení na vyžádání, nikoli při spuštění IDE. Chcete zjistit, které rozšíření dopad spuštění, řešení zatížení a zadáním výkonu? Zobrazí se tyto informace v **pomoci** > **Správa výkonu Visual Studio**.

  ![Dialogové okno Možnosti v Visual Studio 2017](../ide/media/vs2017ide-manage-vs-perf.png)

#### <a name="manage-your-extensions-with-roaming-extensions-manager"></a>Správa rozšíření pomocí Správce rozšíření pro Roaming

Je jednodušší a nastavte každý vývojového prostředí obsahovala vaše oblíbená rozšíření, když se přihlásíte k sadě Visual Studio. Nový Správce rozšíření Roaming uchovává informace o všechna vaše oblíbená rozšíření vytvořením synchronizovaného seznamu v cloudu.

Chcete-li zobrazit seznam rozšíření v sadě Visual Studio, klikněte na tlačítko **nástroje** > **rozšíření & aktualizace**a pak klikněte na tlačítko **Správce rozšíření pro Roaming**.

![Visual Studio 2017 – dialogové okno rozšíření a aktualizace](../ide/media/vs2017ide-extensions-and-updates.png)

Správce rozšíření pro Roaming sleduje všechna rozšíření, které nainstalujete, ale můžete vybrat ty, které chcete přidat do vašeho seznamu roamingu.

![Visual Studio 2017 – dialogové okno rozšíření a aktualizace](../ide/media/vs2017ide-RoamingExtensionManager.png)

Pokud použijete Správce rozšíření pro Roaming, existují tři typy ikon na seznamu:

* ![Ikona s roamingem](../ide/media/vs2017ide-roamedicon.png) ***roamingem***: příponu, která je součástí tohoto seznamu roamingu, ale není nainstalovaná na počítači.
  (Můžete nainstalovat tak, že pomocí **Stáhnout** tlačítko.)
* ![Ikona s roamingem a nainstalované](../ide/media/vs2017ide-roamedinstalledicon.png) ***Roamované & nainstalován***: všechna rozšíření, které jsou součástí tohoto seznamu roamingu a nainstalované ve vašem prostředí vývojářů.
  (Pokud se rozhodnete nechcete se bude používat roaming, můžete odebrat tak, že pomocí **zastavit Roaming** tlačítko.)
* ![Ikona nainstalovaná](../ide/media/vs2017ide-installedicon.png) ***nainstalovaná***: všechna rozšíření, která jsou nainstalovaná v tomto prostředí, ale nejsou součástí vašeho seznamu roamingu.
  (Můžete přidat rozšíření do seznamu roamingu pomocí **spustit Roaming** tlačítko.)

Všechny rozšíření, které si stáhnout, když jste přihlášení je přidán do seznamu jako **Roamované & nainstalován**. Rozšíření se pak stane součástí vašeho seznamu roamingu, která umožňuje přístup k němu z libovolného počítače.

### <a name="experience-live-unit-testing"></a>Prostředí za provozu testování částí

V aplikaci Visual Studio Enterprise 2017 za provozu poskytuje bydlíte výsledky testů částí kódu a pokrytí kódu v editoru při jsou kódování testování částí. Funguje s projekty C# a Visual Basic pro rozhraní .NET Framework a .NET Core a podporuje tři systémů testování Mstestu, xUnit a NUnit.

![Live Unit Testing](../ide/media/lut-codewindow.png)

Další informace najdete v tématu [představení Live jednotkové testování](../test/live-unit-testing-intro.md). Seznam nových funkcí v každé verzi Visual Studio Enterprise 2017 najdete v tématu [co je nového v za provozu testování částí](../test/live-unit-testing-whats-new.md).

### <a name="set-up-a-cicd-pipeline"></a>Nastavit kanál CI/CD

#### <a name="automated-testing"></a>Automatizované testování

Automatizované testování je klíčovou součástí žádné DevOps kanálu. Technická dokumentace umožňuje konzistentní a spolehlivě testování a verzí řešení na mnohem kratší cykly. Toky CI/CD (průběžnou integraci a nastavené průběžné doručování) můžete přispět k procesu efektivnější.

Další informace o automatizované testy, najdete v článku [CI/CD kanálu pro automatizované testy v DevOps](https://blogs.msdn.microsoft.com/visualstudioalmrangers/2017/04/20/set-up-a-cicd-pipeline-to-run-automated-tests-efficiently/) příspěvku na blogu.

A další informace o tom, co je nového [nastavené průběžné doručování tools pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) DevLabs rozšíření, najdete v článku [potvrzení s jistotou: potvrzení kvality kódu čas](https://blogs.msdn.microsoft.com/visualstudio/2017/08/21/committing-with-confidence-commit-time-code-quality-information-updated/) příspěvku na blogu.

### <a name="visual-studio-ide-enhancements"></a>Visual Studio IDE vylepšení

#### <a name="use-new-refactorings"></a>Refaktoring pro nové použití

Refaktoring je proces vylepšení kód po byl proveden zápis. Refaktoring změní interní kód beze změny jeho chování. Přidáme nové refaktoring často; Tady je pár:

* Přidejte parametr (z CallSite)
* Generovat přepsání
* Přidat pojmenované argument
* Přidání null kontroly pro parametry
* Vložit číslice oddělovačů do literály
* Změňte základní pro číselné literály (například šestnáctkových na binární)
* Převod Pokud přepínače
* Odebrat nepoužité proměnnou

Další informace najdete v tématu [rychlé akce](../ide/common-quick-actions.md).

#### <a name="interact-with-git"></a>Pracovat s Gitem

Když pracujete s projektem v sadě Visual Studio, můžete nastavit a rychle potvrzení a publikování kódu službě Git. Můžete také spravovat vaše úložiště Git pomocí nabídky kliknutí ze tlačítka v pravém dolním rohu rozhraní IDE.

![Visual Studio 2017 komunikuje s dialogu Git](../ide/media/vsIDE-GitInteraction.png)

#### <a name="experience-improved-navigation-controls"></a>Ovládací prvky pro navigaci vylepšené prostředí

Navigace prostředí můžete získat z A a B s větší jistotou rušeni aktualizována.

* **Novinka v 15.4**: **přejít k definici** (**Ctrl**+**klikněte na tlačítko** nebo **F12**) &ndash; myši uživatelů máte snadný způsob, jak přejít k definici člena stisknutím **Ctrl** a pak levým na člen. Stisknutím **Ctrl** a ukazatele myši na symbol kód bude underline ho a zapnout na odkaz. V tématu [přejít k definici a prohlížení definice](../ide/go-to-and-peek-definition.md) Další informace.

* **Přejít na implementaci** (**Ctrl**+**F12**) &ndash; přejde z jakékoli základní typ nebo člen na její různé implementace.

* **Přejděte na všechny** (**Ctrl**+**T** nebo **Ctrl**+**,**) &ndash; přejděte přímo do každé prohlášení souboru nebo typ/člen nebo symbol. Můžete si na seznam výsledků nebo filtrovat, použijte syntaxi dotazu (například "f searchTerm" pro soubory.), "t searchTerm" pro typy atd.

  ![Vylepšené, přejděte na všechny](../ide/media/vs2017ide-navigation-go-to.png)

* **Najít všechny odkazy** (**Shift**+**F12**) &ndash; s zabarvení syntaxe, můžete najít všechny odkaz výsledky seskupovat podle kombinace projektu, definice a cestu. Je také možné "zamknout" výsledky, aby mohl pokračovat k nalezení dalších odkazů na bez ztráty původní výsledky.

  ![Nový nástroj Najít všechny odkazy](../ide/media/vs2017ide-find-all-references.png)

* **Struktury vizualizér** &ndash; s tečkami, šedé svislé čáry (odsazení příručky) fungovat jako zajímavá v kódu kontextu v rámci vaší rámce zobrazení. Můžete je rozpoznat z oblíbených nástrojů Power produktivitu. Můžete je používat k vizualizaci a zjistit, jaké blok kódu můžete začít kdykoli bez nutnosti posouvání. Ukazatele myši na řádky zobrazí popis, který ukazuje otevření tohoto bloku a jejích nadřazených tříd. Je k dispozici pro všechny jazyky podporované prostřednictvím TextMate gramatika, jakož i C#, Visual Basic a XAML.

  ![Visual Studio 2017 struktura vizualizéru](../ide/media/vsIDE-StructureVisualizer.png)

Další informace o nových funkcích produktivitu najdete v tématu [produktivitu při Visual Studio 2017](https://blogs.msdn.microsoft.com/visualstudio/2016/11/28/productivity-in-visual-studio-2017-rc/) příspěvku na blogu podle Wilson blogu Thomase značky.

### <a name="visual-c"></a>Visual C++

Se zobrazí několik vylepšení v sadě Visual Studio, jako je například distribuci základní pokyny C++ pomocí sady Visual Studio, aktualizace kompilátor přidáním rozšířenou podporu pro C ++ 11 a C++ funkce přidání a aktualizace funkcí knihovny jazyka C++. Vylepšili jsme také výkon C++ IDE, úlohy instalace a další.

Taky jsme vyřešili více než 250 chyb a hlášené problémy v kompilátoru a nástroje, mnoho odeslané zákazníky pomocí [komunity vývojářů pro jazyk C++](https://developercommunity.visualstudio.com/spaces/62/index.html "komunity vývojářů pro jazyk C++").

Úplné podrobnosti najdete v tématu [co je nového pro Visual C++ v Visual 2017](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio) stránky.

### <a name="debugging-and-diagnostics"></a>Ladění a Diagnostika

#### <a name="run-to-click"></a>Běžet do kliknutí

Teď můžete snadno přeskočit během ladění bez nastavení boru přerušení na řádek, který chcete zastaví. Po zastavení v ladicím programu stačí kliknout na ikonu, která se zobrazí vedle řádek kódu. Váš kód bude spustit a zastavit na tomto řádku při příštím je dosáhl v kódové cestě.

![Ladění jazyka Visual Studio 2017 - spuštění klikněte na](../ide/media/vs2017ide-RunToClick.png)

#### <a name="the-new-exception-helper"></a>Nový Pomocník výjimka

Nového pomocníka výjimka můžete zobrazit vaše výjimka informace na Přehled. Informace jsou poskytovány compact formuláře s okamžitým přístupem k vnitřním výjimkám. Po dokončení diagnostiky NullReferenceException, můžete rychle zjistit, co měl hodnotu null právo uvnitř pomocníka výjimka.

![Dialogové okno nového pomocníka výjimka v sadě Visual Studio](../ide/media/vs2017ide-ExceptionHelper.png)

Další informace najdete v tématu [pomocí nového pomocníka výjimka v sadě Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/) příspěvku na blogu.

#### <a name="snapshots-and-intellitrace-step-back"></a>Snímky a zpětný krok IntelliTrace

**Novinka v 15,5**: zpětný krok IntelliTrace automaticky vytvoří snímek vaší aplikace v každé zarážek a ladicí program krok události. Zaznamenaná snímky umožňují přejděte zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti. IntelliTrace zpětný krok vám může ušetřit čas když chcete zobrazit předchozí stav aplikace, ale nechcete, aby se znovu spustit ladění nebo znovu vytvořte stav požadované aplikace.

Můžete vyhledat a zobrazit snímky pomocí **krok zpětné** a **krok dál** tlačítka v **ladění** panelu nástrojů. Tato tlačítka přejděte události, které se zobrazují v **události** ve **diagnostické nástroje** okno. Krokování zpětně nebo dopředu na událost automaticky aktivuje historické ladění na vybrané události.

![Dialogové okno nového pomocníka výjimka v sadě Visual Studio](../debugger/media/intellitrace-step-back-icons-description.png  "krok zpět a jejich předávání tlačítka")

Další informace najdete v tématu [zobrazit snímky IntelliTrace zpětným krok pomocí](../debugger/how-to-use-intellitrace-step-back.md) stránky.

### <a name="containerization"></a>Rozdělení do kontejnerů

Kontejnery můžete poskytnout hustotu aplikace vyšší a nižší náklady na nasazení společně s zvýšení produktivity a flexibility DevOps.

#### <a name="docker-container-tooling"></a>Nástrojů kontejner docker

**Novinka v 15,5**:

* Visual Studio obsahuje nástroje pro Docker kontejnery, které teď podporují Dockerfiles několika fází, které zjednodušit vytváření optimalizovaných bitových kopií kontejneru.
* Když otevřete projekt, který podporuje Docker, bude Visual Studio ve výchozím nastavení automaticky vyžadovat, sestavovat a spouštět nezbytné kontejnerové image na pozadí. Tuto funkci můžete vypnout pomocí nastavení **Automaticky spustit kontejnery na pozadí** v sadě Visual Studio.

## <a name="cloud-app-development-with-azure"></a>Vývoj aplikací cloudu s Azure

### <a name="azure-functions-tools"></a>Nástroje Azure funkce

Jako součást úlohy "Azure development" jsme zahrnuli nástroje umožňující vývoj Azure functions pomocí předem kompilovaném knihovny tříd jazyka C#. Nyní můžete vytvořit, spustit a ladění na místním vývojovém počítači a potom publikovat přímo do Azure ze sady Visual Studio.

Další informace najdete v tématu [Azure Functions tools pro Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-develop-vs) stránky.

### <a name="debug-live-aspnet-apps-using-snappoints-and-logpoints-in-live-azure-applications"></a>Ladění za provozu aplikace ASP.NET pomocí snappoints a logpoints v za provozu aplikace Azure

**Novinka v 15,5**: ladicím programu snímku pořídí snímek aplikací v provozním když provede kód, který vás zajímá. Dáte pokyn, aby ladicí program na pořízení snímku, nastavte snappoints a logpoints ve vašem kódu. Ladicí program umožňuje zobrazit přesně kde došlo k chybě, bez vlivu na provoz produkční aplikace. Ladicí program snímku můžete výrazně zkrátit dobu potřebnou k vyřešení problémů, ke kterým došlo v produkčním prostředí.

Snímek kolekce je k dispozici pro následující webové aplikace běžící v Azure App Service:

* Aplikace ASP.NET spuštěné na rozhraní .NET Framework 4.6.1 nebo novější.
* ASP.NET Core aplikací běžících na .NET Core 2.0 nebo novější na systému Windows.

Další informace najdete v tématu [ladění za provozu aplikace ASP.NET pomocí snappoints a logpoints](../debugger/debug-live-azure-applications.md).

## <a name="windows-app-development"></a>Vývoj aplikací pro systém Windows

### <a name="universal-windows-platform"></a>Univerzální platforma pro Windows

Univerzální platformu Windows (UWP) je platforma aplikace pro Windows 10. Můžete vyvíjet aplikace pro UPW s jedinou sadu rozhraní API, balíček aplikace jeden a jedno úložiště k dosažení všech zařízeních s Windows 10 &ndash; počítač, tablet, phone, Xbox, HoloLens, Surface Hub a další. UWP podporuje jiné velikosti obrazovky a mnoha interakce, ať to dotykového ovládání, myši a klávesnice, herní zařízení nebo pera. Základem aplikace UWP je představu, uživatelé mají svoje prostředí na všech jejich zařízeních jsou mobilní a že chtějí používat, ať zařízení pro na prováděné úloze je nejvíce vhodnou nebo produktivitu.

 ![Univerzální platforma pro Windows](../cross-platform/media/uwp_coreextensions.png)

Vyberte si jazyk upřednostňované vývoj&mdash;z jazyka C#, Visual Basic, C++ nebo JavaScript&mdash;k vytvoření aplikace pro univerzální platformu Windows pro zařízení s Windows 10. Visual Studio 2017 poskytuje šablony aplikace UPW pro jednotlivé jazyky, které umožňují vytvořit jeden projekt pro všechna zařízení. Po dokončení práce, můžete vytvořit balíček aplikace a odešlete ji do Microsoft Store z Visual Studia schválení vaší aplikace zákazníkům na jakékoli zařízení s Windows 10.

**Novinka v 15,5**: Visual Studio 2017 verze 15,5 poskytuje nejlepší podporu pro Windows 10 patří Creators aktualizace SDK (10.0.16299.0). Aktualizace Windows 10 patří Creators také přináší mnoho vylepšení pro UPW vývojáře. Tady jsou některé z největších změn: 

* **Podpora pro rozhraní .NET Standard 2.0**<br/>Kromě nasazení moderní aplikace je aktualizace Windows 10 patří Creators první verzi Windows 10 kvůli zajištění podpory standardní rozhraní .NET 2.0. Prakticky [.NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/) je implementace reference knihovny základní třídu, která můžete implementovat libovolnou platformu .NET. Cílem .NET Standard je zajistit co největší pro vývojáře .NET sdílet kód na jakékoli platformě .NET, kterou si zvolí při práci.
* **Nejlepší UWP a Win32**<br/>Jsme vylepšili platformu Windows 10 s [plochy most](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-root) k vylepšit Windows 10 pro všechny vývojáře .NET, zda je jejich aktuální aktivní UWP WPF, Windows Forms nebo Xamarin. S novým typem projektu balení aplikací ve Visual Studio 2017 verze 15,5 můžete vytvořit balíčky aplikace systému Windows pro projekty WPF nebo Windows Forms, podobně jako u projektů UPW. Po balíček aplikace se všechny aplikace pro Windows 10 získat výhody nasazení a máte možnost distribuovat přes Microsoft Store (pro spotřebitele aplikace) nebo Microsoft Store pro firmy a Education. Protože zabalených aplikací mít přístup k úplné plochy UWP API a rozhraní API Win32 na ploše, můžete nyní modernizovat aplikace WPF a Windows Forms postupně s funkcemi UWP rozhraní API a Windows 10. Kromě toho můžete zahrnout vaše Win32 komponenty ve svých aplikacích UPW, které light na ploše se všemi funkcemi Win32.

Další informace o UWP najdete v tématu [vývoj aplikací pro univerzální platformu Windows (UWP)](../cross-platform/develop-apps-for-the-universal-windows-platform-uwp.md) stránky.

## <a name="mobile-app-development"></a>Vývoj mobilních aplikací

### <a name="xamarin"></a>Xamarin

Jako součást úlohy "Mobilní vývoj s .NET" vývojáři, kteří znají C# .NET a Visual Studio doručovat nativní aplikace pro Android, iOS a Windows pomocí Xamarin. Vývojářům umožňuje využívat stejné napájení a produktivitu při práci s funkcí Xamarin pro mobilní aplikace, včetně vzdáleného ladění na zařízení Android, iOS a Windows&mdash;bez nutnosti další nativní kódování jazyky jako jazyka Objective-C nebo Java.

Další informace najdete v tématu [Visual Studio a Xamarin](../cross-platform/visual-studio-and-xamarin.md) stránky.

### <a name="entitlements-editor"></a>Editor oprávnění

**Novinka v 15.3**: pro vaše potřeby vývoj pro iOS, jsme přidali samostatné editor oprávnění. Obsahuje uživatelsky přívětivý uživatelské rozhraní, které lze snadno procházet. Chcete-li jej spustit, dvakrát klikněte na vaše *entitlements.plist* souboru.

![Editor nároku pro Xamarin](../ide/media/xamarin-entitlements-editor.png)

### <a name="visual-studio-tools-for-xamarin"></a>Visual Studio Tools pro Xamarin

**Novinka v 15.4**: Xamarin Live umožňuje vývojářům nepřetržitě nasazení, testování a ladění své aplikace, přímo na zařízení iOS a Android. Po stáhnout přehrávač Live Xamarin&mdash;dostupná v App Storu nebo na webu Google Play&mdash;můžete spárovat zařízení pomocí sady Visual Studio a mohla úplně změnit způsob sestavení mobilní aplikace. Tato funkce je teď zahrnutá v sadě Visual Studio a jde povolit v nabídce **Nástroje** > **Možnosti** > **Xamarin** > **Jiné** > **Povolit Xamarin Live Player**.

![Animace pár Xamarin Live Player, nasazení a režimy provozu úpravy](../ide/media/xamarinliveplayer.gif)

### <a name="visual-studio-app-center"></a>Centrum aplikace Visual Studio

**Nové v 15,5**: Centrum aplikace Visual Studio&mdash;tedy nyní obecně dostupné pro Android, iOS, Windows a systému macOS aplikace&mdash;obsahuje všechno, co musíte provést správu životního cyklu aplikací, včetně automatizovaných sestaveních testování v reálném zařízení v cloudu, distribuci do beta testery a obchody s aplikacemi a z reálného využití prostřednictvím havárií a analýzy dat monitorování. Aplikace napsané v Objective-C, Swift, Java, C#, Xamarin a reagovat nativní jsou podporovány v rámci všech funkcí.

  ![Centrum aplikace Visual Studio testovacího prostředí](../ide/media/app-center-test-env.png)

Další informace najdete v tématu [Introducing aplikace Center: vytváření, testování, distribuci a monitorování aplikací v cloudu](https://blogs.msdn.microsoft.com/vsappcenter/introducing-visual-studio-app-center/) příspěvku na blogu.

## <a name="cross-platform-development"></a>Vývoj pro různé platformy

### <a name="redgate-data-tools"></a>Nástroje Redgate Data

Rozšířit možnosti DevOps pro vývoj databází systému SQL Server, jsou nyní Redgate nástrojů Data k dispozici v sadě Visual Studio.

Součástí Visual Studio 2017 Enterprise:

* [Základní ReadyRoll Redgate](http://www.red-gate.com/products/sql-development/readyroll/entrypage/microsoft-and-readyroll?utm_source=microsoft&utm_medium=link&utm_campaign=readyroll&utm_term=docs-newinvs) změny spolu s aplikací změny databáze pomáhá vyvíjet skripty pro migraci, správu změn databáze pomocí správy zdrojového kódu a bezpečně automatizaci nasazení systému SQL Server.
* [Výzva základní SQL Redgate](http://www.red-gate.com/products/sql-development/sql-prompt/entrypage/microsoft-and-sql-prompt?utm_source=microsoft&utm_medium=link&utm_campaign=sqlprompt&utm_term=docs-newinvs) pomáhá napíšete SQL rychle a přesně za pomoci inteligentního code dokončení. SQL Prompt automaticky dokončuje databázové a systémové objekty a klíčová slova a během psaní nabízí návrhy sloupců. Výsledkem čisticí kód a méně chyby vzhledem k tomu, že nemusíte pamatovat každý název sloupce nebo aliasem.

Všechny edice Visual Studio 2017 součástí:

* [Vyhledávání SQL Redgate](http://www.red-gate.com/products/sql-development/sql-search/?utm_source=microsoft&utm_medium=link&utm_campaign=sqlsearch&utm_term=docs-newinvs) zvyšuje úroveň produktivity vám pomáhá rychle najít SQL fragmenty a objektů mezi více databází.

Další informace najdete v tématu [Redgate nástrojů Data v aplikaci Visual Studio 2017](https://blogs.msdn.microsoft.com/visualstudio/2017/03/07/redgate-data-tools-in-visual-studio-2017/) příspěvku na blogu.

### <a name="net-core"></a>.NET Core

.NET core obecné účely, modulární, napříč platformami a .NET Standard s otevřeným zdrojem implementace a obsahuje řadu stejná rozhraní API jako rozhraní .NET Framework.

Platformy .NET Core se provádí z několika komponent, které zahrnují spravované kompilátory, modul runtime, knihovny základní třídy a množství modely aplikace, jako je ASP.NET Core. .NET core podporuje tři hlavní operační systémy: Windows, Linux a systému macOS. .NET Core můžete použít v zařízení, cloud a scénáře vložených/IoT.

A teď obsahuje podporu Docker.

**Novinka v 15.3**: Visual Studio 2017 verze 15.3 podporuje vývoj .NET Core 2.0. Použití rozhraní .NET 2.0 základní vyžaduje stahování a instalace .NET Core 2.0 SDK samostatně.

Další informace najdete v tématu [.NET Core průvodce](/dotnet/core/index) stránky.

## <a name="games-development"></a>Vývoj her

### <a name="visual-studio-tools-for-unity"></a>Visual Studio Tools for Unity

Jako součást úlohy "Vývoj her pro Unity" jsme zahrnuli nástroje umožňující vývoj napříč platformami vytváření 2D a 3D hry a interaktivní obsah. Po vytvoření a publikování na 21 platformy, včetně všechny mobilní platformy, WebGL, Mac, počítače a Linux plocha, web nebo konzoly pomocí Visual Studio 2017 a Unity 5.6.

Další informace najdete v tématu [Visual Studio Tools for Unity](../cross-platform/visual-studio-tools-for-unity.md) stránky.

## <a name="ai-development"></a>Vývoj pro AI

### <a name="visual-studio-tools-for-ai"></a>Visual Studio Tools for AI

**Novinka v 15,5**: použijte produktivitu funkce sady Visual Studio pro urychlení AI inovací ještě dnes. Použijte předdefinovaný kód editor funkce, jako jsou zvýraznění syntaxe, IntelliSense a text automatické formátování. Můžete interaktivně otestovat váš přímý learning aplikací ve vašem místním prostředí pomocí procházení po kroku ladění na místní proměnné a modely.

  ![Přímý učení IDE](../ai/media/about/ide.png)

Další informace najdete v tématu [Visual Studio Tools for AI](../ai/about-ai-tools.md) stránky.

## <a name="whats-next"></a>Co je další

Nové funkce, které můžou váš vývojový i lepší prostředí často aktualizujeme Visual Studio 2017. Tady je shrnutí některých naše nejdůležitějším aktualizací, které jsou ve verzi preview experimentální:

* **[Live sdílené složky](https://visualstudio.microsoft.com/services/live-share/)**, nový nástroj, který umožňuje sdílet codebase a jeho kontextu, teammate a získat rychlých obousměrný spolupráce přímo z Visual Studia. S Live sdílenou složkou teammate můžete číst, přejděte, upravit a ladění projektu, který je sdílíte a to provést bez problémů a bezpečně.<br><br>Další informace najdete v tématu [Live – nejčastější dotazy sdílené složky](/visualstudio/liveshare/faq).<br><br>
* **[IntelliCode](https://visualstudio.microsoft.com/services/intellicode/)**, novou funkci, která vylepšuje vývoj softwaru pomocí AI zajistit lepší podporou kontextu kód dokončování Průvodce vývojářům kódu vzory a styly jejich týmu, najít problémy obtížné catch kódu , a zkontroluje kód fokus na oblasti, které skutečně vás právě zajímají. <br><br>Další informace najdete v tématu [– nejčastější dotazy IntelliCode](../ide/not-in-toc/intellicode-faq.md).

Chcete vědět více o tom, co else je ve službě funguje pro Visual Studio 2017? Najdete v článku [Visual Studio plán](/visualstudio/productinfo/vs2018-roadmap) stránky.

## <a name="contact-us"></a>Kontaktujte nás

 Proč odeslat zpětnou vazbu k sadě Visual Studio team? Vzhledem k tomu, vážně jsme trvat názory zákazníků. Jednotky většinu co můžeme udělat.

Pokud chcete navrhnout zlepšení o tom, jak jsme můžete zlepšit Visual Studio, nebo Další informace o možnostech podpory produktu, naleznete v tématu [kontaktujte nás](../ide/talk-to-us.md) stránky.

### <a name="report-a-problem"></a>Nahlásit problém

 V některých případech zprávu není dost pro vyjádření celkovému dopadu na problém, která byla zjištěna. Pokud dojde zablokování, havárie nebo jiné problémy s výkonem, můžete snadno sdílet zkopírujte kroky a podpůrné soubory (například snímky obrazovky a trasování a haldy soubory výpisů) s námi pomocí **nahlásit problém** nástroj. Další informace o tom, jak tento nástroj použít, najdete v článku [postup nahlásit problém](how-to-report-a-problem-with-visual-studio-2017.md) stránky.

## <a name="see-also"></a>Viz také:

* [Poznámky k verzi Visual Studio 2017](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default)
* [Co je nového ve Visual C++](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio)
* [Co je nového v jazyce C#](/dotnet/csharp/whats-new)
* [Co je nového pro Team Foundation Server](/tfs/server/whats-new?view=vsts)
* [Co je nového v sadě Visual Studio pro Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/)
