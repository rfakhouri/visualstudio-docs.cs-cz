---
title: Přehled Visual Studio 2017
ms.date: 06/01/2018
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
ms.openlocfilehash: d9e1149803516e0b411bfef1da06fd6e1af9a12f
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282723"
---
# <a name="visual-studio-ide-overview"></a>Přehled Visual Studio IDE

Visual Studio interaktivní vývojové prostředí (IDE) je tvůrčí odrazový můstek, můžete použít k zobrazení a úpravy kódu a pak ladění, vytvoření a publikování aplikace.

Visual Studio je k dispozici pro systém Windows a macu. [Visual Studio pro Mac](/visualstudio/mac/) obsahuje řadu stejných funkcí jako Visual Studio 2017 a je optimalizovaná pro vývoj napříč platformami a mobilních aplikací.

Tento článek se zaměřuje na Visual Studio 2017 pro Windows. Ho vás seznámí s základní funkce rozhraní IDE. Projdeme některé věci, které můžete provést pomocí sady Visual Studio, včetně vytvoření jednoduché projektu, jako kódování podpory pomocí IntelliSense a ladění aplikace a zobrazit tak hodnotu proměnné během provádění tohoto programu. Také provedeme prohlídka různé nástroje Windows.

## <a name="install-the-visual-studio-ide"></a>Instalace sady Visual Studio IDE

Abyste mohli začít, [Stáhnout Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) a nainstalujte ho v systému.

Modulární instalační program vám umožňuje vybrat a nainstalovat *úlohy*, což jsou skupiny součástí, které jsou potřebné pro programovací jazyk nebo platformu dáváte přednost. Podle pokynů pro [vytváření program](#create-a-program), je nutné vybrat **vývoj pro různé platformy .NET Core** zatížení během instalace. Témata rychlý start, jako například [Začínáme s C++ v sadě Visual Studio](getting-started-with-cpp-in-visual-studio.md), obsahovat pokyny k instalaci dalších zatížení.

![Instalační program pro Visual Studio](../ide/media/overview-net-core-workload.png)

Při prvním spuštění sady Visual Studio, můžete volitelně Přihlaste se pomocí účtu Microsoft nebo váš pracovní nebo školní účet.

## <a name="tour-of-the-ide"></a>Přehled používání prostředí IDE

Následující obrázek ukazuje tak, abyste získali visual Přehled sady Visual Studio, Visual Studio s otevřít projekt spolu s několika okna klíče nástrojů, které budou s největší pravděpodobností používat:

![Visual Studio IDE](../ide/media/visualstudioide.png)

- [Průzkumník řešení](../ide/solutions-and-projects-in-visual-studio.md) umožňuje zobrazit, přejděte a spravovat soubory s kódem. Průzkumník řešení pomáhá organizovat kód seskupením soubory do řešení a projekty.

- [Editor](../ide/writing-code-in-the-code-and-text-editor.md) okno, kde budete pravděpodobně tráví většinu doby, zobrazuje kódu a umožní vám upravit zdrojový kód a návrh uživatelského rozhraní.

- [Výstup – okno](../ide/reference/output-window.md) je, kde Visual Studio odešle jeho oznámení, jako je ladění a chybové zprávy, upozornění kompilátoru, publikování stavové zprávy a další. Každý zdroj zpráva má vlastní kartě.

- [Team Explorer (VSTS)](/vsts/user-guide/work-team-explorer) slouží ke sledování pracovní položky a sdílet s ostatními kódu pomocí technologie pro řízení verzí, jako třeba [Git](https://git-scm.com/) a [Team Foundation verze ovládacího prvku (TFVC)](/vsts/tfvc/overview).

Toto jsou některé další funkce oblíbených produktivitu v sadě Visual Studio:

- [Refaktoring](../ide/refactoring-in-visual-studio.md) zahrnuje operace, jako je inteligentního přejmenování proměnných Přesun vybrané řádky kódu do samostatné funkce, přesunutí kódu do jiných umístění, způsob parametry funkce a další.

   ![Refaktoring](../ide/media/VSIDE_refactor.png)

- [IntelliSense](../ide/using-intellisense.md) je také souhrnný název pro sadu oblíbených funkcí, které zobrazují informace o typu o kódu přímo v editoru a v některých případech zápisu malých bits kódu pro vás. Je to jako mít základní dokumentace vložené v editoru ušetří práci s k vyhledání informací o typu v okně samostatné nápovědy. Funkce IntelliSense se liší podle jazyka. Další informace najdete v tématu [C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ IntelliSense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md), a [jazyka Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md). Některé funkce IntelliSense v práci na následujícím obrázku:

   ![Seznam členů v sadě Visual Studio](../ide/media/vs2017_Intellisense.png)

- [Snadné spuštění](../ide/reference/quick-launch-environment-options-dialog-box.md) vyhledávacího pole je skvělým způsobem, jak rychle najít, co je třeba v sadě Visual Studio. Právě začněte psát název ať hledáte a Visual Studio zobrazí výsledky, které dostanete přesně, kde chcete přejít. **Snadné spuštění** taky obsahuje odkazy ukazuje, že počáteční **instalační program Visual Studio** pro všechny úlohy nebo jednotlivých součástí.

   ![Rychlé spuštění vyhledávacího pole](../ide/media/VSIDE_Tour_QuickLaunch.png)

- **Podtržení vlnovkou** jsou podtržení vlnovkami, které vás upozorní na chyby nebo potenciální problémy ve vašem kódu v reálném čase během psaní. To umožňuje opravit okamžitě bez čekání na chyby zjištěné při kompilaci nebo čas spuštění. Pokud je ukazatel myši nad vlnovka, zobrazí další informace o této chybě. Žárovky může zobrazit i na levém okraji s akcemi pro chybu ověřování opravte. Další informace najdete v tématu [rychlé akce](../ide/quick-actions.md).

   ![Podtržení vlnovkou](../ide/media/vs2017_squiggle.png)

- [Hierarchie volání](../ide/reference/call-hierarchy.md) okno můžete otevřít v místní nabídce textového editoru zobrazíte metody, které volání a jsou volány, metoda pod pomocí kurzoru (bod vložení).

   ![Hierarchie volání – okno](../ide/media/VSIDE_call_hierarchy.png)

- [Codelensu](../ide/find-code-changes-and-other-history-with-codelens.md) umožňuje najít odkazy a změny provedené v kódu, propojené chyby, pracovní položky, kód recenze a testování částí všechny bez opuštění editoru.

   ![Codelensu](../ide/media/codelensoverview.png)

- [Funkce Náhled definice](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) v okně se zobrazí vložené definice metoda nebo typ bez nutnosti opustit váš aktuální kontext.

   ![Funkce Náhled definice](../ide/media/VSIDE_peek_definition.png)

- [Přejít k definici](../ide/go-to-and-peek-definition.md) možnost místní nabídky přejdete přímo na místě, kde je definována funkce nebo objektu. Další příkazy navigace jsou k dispozici také kliknutím pravým tlačítkem myši v editoru.

   ![Přechod na definici](../ide/media/VSIDE_go_to_definition.png)

## <a name="create-a-program"></a>Vytvořit program

Umožňuje podrobné informace a vytvořit nové, jednoduchý program.

1. Otevřete Visual Studio. V nabídce zvolte **soubor** > **nový** > **projektu**.

  ![Soubor > Nový projekt v řádku nabídek](../ide/media/VSIDE_Tour_NewProject1.png)

1. **Nový projekt** dialogové okno zobrazí několik projektu *šablony*. Šablona obsahuje základní soubory a nastavení potřebné pro typ daného projektu. Vyberte **.NET Core** kategorii v **Visual C#** a potom zvolte **konzolové aplikace (.NET Core)** šablony. V **název** textového pole, typ **HelloWorld**a pak vyberte **OK** tlačítko.

  ![Šablony aplikace .NET core](../ide/media/overview-new-project-dialog.png)

   Visual Studio vytvoří projekt. Je jednoduchou aplikaci "Hello World", která volá <xref:System.Console.WriteLine?displayProperty=nameWithType> metodu pro zobrazení řetězcového literálu "Hello, World!" v okně konzoly.

  > [!NOTE]
  > Pokud nevidíte **.NET Core** kategorie, je třeba nainstalovat **vývoj pro různé platformy .NET Core** zatížení. To pokud chcete udělat, vyberte **otevřete instalační program Visual Studio** odkaz na spodní levé straně **nový projekt** dialogové okno. Po **instalační program Visual Studio** otevře, posuňte se dolů a vyberte **vývoj pro různé platformy .NET Core** zatížení a potom vyberte **upravit**.

   Zanedlouho byste měli vidět přibližně takto:

   ![Visual Studio – sada IDE](../ide/media/overview-ide-console-app.png)

   Kód jazyka C# pro vaši aplikaci se zobrazí v okně editor, které zabírají většina místa. Všimněte si, že je text automaticky obarvené k označení různých aspektů kód, jako jsou klíčová slova a typy. Kromě toho malé, svislá přerušované čáry v kódu označují, které složené závorky odpovídat navzájem a čísla řádků vám pomohou vyhledat kód později. Můžete použít znaky minus malé, zabalené sbalit nebo rozbalte kódu. Tento kód osnovy funkce umožňuje skrýt kódu, které nepotřebujete, pomáhá minimalizovat zbytečné soubory na obrazovce.

   Soubory projektu, které jsou uvedené na pravé straně v okně názvem **Průzkumníku řešení**.

  ![Visual Studio IDE s červenou polí](../ide/media/overview-ide-console-app-red-boxes.png)

  Existují jiné nabídky a nástroje systému windows k dispozici, ale umožňuje přesun chvíli.

1. Nyní spusťte aplikaci. To provedete tak, že zvolíte **spustit bez ladění** z **ladění** nabídky v řádku nabídek. Můžete také stisknout **Ctrl**+**F5**.

  ![Ladění > Spustit bez ladění nabídky](../ide/media/overview-start-without-debugging.png)

  Visual Studio vytvoří aplikaci a otevře se okno konzoly se zprávou **Hello, World!**. Nyní máte spuštěné aplikaci!

  ![Okno konzoly](../ide/media/overview-console-window.png)

1. Zavřete okno konzoly, stisknutím libovolné klávesy.

1. Přidejme nějaký další kód do aplikace. Přidejte následující C# kód před řádek, která uvádí, že `Console.WriteLine("Hello World!");`:

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   Tento kód zobrazí **jaké je vaše jméno?** okno konzoly a potom počká, dokud uživatel nezadá nějaký text, za nímž následuje **Enter** klíč.

1. Změňte řádek, která uvádí, že `Console.WriteLine("Hello World!");` na následující kód:

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. Znovu spusťte aplikaci tak, že vyberete **ladění** > **spustit bez ladění** nebo stisknutím kombinace kláves **Ctrl**+**F5**.

   Visual Studio znovu sestaví aplikace a otevře okno konzoly a vás vyzve k zadání vaše jméno.

1. Zadejte název v okně konzoly a stiskněte klávesu **Enter**.

   ![Vstup okna konzoly](media/overview-console-input.png)

1. Stisknutím libovolné klávesy zavřete okno konzoly a zastavit spuštěný program.

## <a name="use-refactoring-and-intellisense"></a>Refaktoring a IntelliSense

Podívejme se na několik způsobů, jak který [refaktoring](refactoring-in-visual-studio.md) a [IntelliSense](using-intellisense.md) může pomoci používáte kódové efektivněji.

Nejprve umožňuje přejmenovat `name` proměnné:

1. Dvakrát klikněte `name` proměnná ji vyberte.

1. Zadejte nový název pro proměnnou, `username`.

   Všimněte si, že se kolem proměnnou a žárovky zobrazí šedé pole se zobrazí u okraje.

1. Vyberte ikonu žárovky k zobrazení dostupných [rychlé akce](quick-actions.md). Vyberte **přejmenovat (name) k 'uživatelského jména'**.

   ![Přejmenujte akce v sadě Visual Studio](media/rename-quick-action.png)

   Proměnná se přejmenuje v projektu, který je v našem případě pouze dvě místech.

   ![Animovaný gif zobrazující přejmenování refaktoring v sadě Visual Studio](media/rename-refactoring.gif)

1. Nyní Podívejme se na technologii IntelliSense. Níže na řádku, která uvádí, že `Console.WriteLine($"\nHello {username}!");`, typ **data a času nyní = data a času.**.

   Pole zobrazuje členů <xref:System.DateTime> třídy. Kromě toho zobrazí popis aktuálně vybraného člena v samostatném poli.

   ![IntelliSense seznam členů v sadě Visual Studio](media/intellisense-list-members.png)

1. Vyberte člena s názvem **nyní**, což je vlastnost třídy, dvojitým kliknutím na něm nebo stisknutím **kartě**. Dokončení řádek kódu přidáním středníkem **;**.

1. Níže, napište nebo zkopírujte následující řádky kódu:

   ```csharp
   int dayOfYear = now.DayOfYear;

   Console.Write("Day of year: ");
   Console.WriteLine(dayOfYear);
   ```

   > [!TIP]
   > <xref:System.Console.Write%2A?displayProperty=nameWithType> mírně liší na <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> v, že po vytiskne nepřidá ukončení řádku. To znamená, že další část textu, které je odesláno výstup bude tisk na stejném řádku. V každé z těchto metod můžete podržet ve vašem kódu jejich popis.

1. V dalším kroku použijeme refaktoring znovu Chcete-li další stručným kód. Klikněte na proměnnou `now` v řádku `DateTime now = DateTime.Now;`.

   Všimněte si, že se málo šroubovák zobrazí ikona rozpětí z daného řádku.

1. Klikněte na ikonu šroubovák a počkejte, Visual Studio je k dispozici. V takovém případě se zobrazuje [dočasné vloženou proměnnou](reference/inline-temporary-variable.md) refaktoringu bez změny chování celkové odebrat řádek kódu:

   ![Vložené dočasné proměnné refaktoring v sadě Visual Studio](media/inline-temporary-variable-refactoring.png)

1. Klikněte na tlačítko **dočasné vloženou proměnnou** Refaktorovat kód.

1. Spusťte program znovu stisknutím **Ctrl**+**F5**. Výstup bude vypadat přibližně takto:

   ![Okno konzoly s výstupem programu](../ide/media/overview-console-final.png)

## <a name="debug-code"></a>Ladění kódu

Při psaní kódu, budete muset spustit a otestovat ji pro chyby. Ladění systému Visual Studio umožňuje krok prostřednictvím kódu jeden příkaz v čase a zkontrolovat proměnné narazíte. Můžete nastavit zarážky, které jsou pouze dosáhl při splnění zadané podmínky. Můžete sledovat hodnoty proměnných, jako je kód spuštěn a další.

Umožňuje nastavit zarážky zobrazíte hodnotu `username` proměnná při "v cestě" program.

1. Najít řádek kódu, která uvádí, že `Console.WriteLine($"\nHello {username}!");`. Chcete-li nastavit zarážky tento řádek kódu, který je nastavit, aby program pozastavit provádění na tomto řádku, klikněte na tlačítko na levém okraji editoru. Můžete také kliknout na tlačítko kdekoli na řádek kódu a stiskněte klávesu **F9**.

   Červené kolečko se zobrazí v daleko levým okrajem a kód se zobrazí červeně.

   ![Breakpoint – na řádek kódu v sadě Visual Studio](media/breakpoint.png)

1. Spuštění ladění výběrem **ladění** > **spustit ladění** nebo stisknutím kombinace kláves **F5**.

1. Když v okně konzoly se zobrazí a požádá o název, zadejte ho a stiskněte klávesu **Enter**.

   Všimněte si, že se fokus vrátí do editoru kódu v sadě Visual Studio a řádek kódu se zarážkou zvýrazněn žlutě. Znamená to, že je na další řádek kódu, který spustí program.

1. Umístěte ukazatel myši nad `username` proměnné zobrazíte jeho hodnotu. Alternativně můžete můžete kliknout pravým tlačítkem na `username` a vyberte **Přidat kukátko** přidat proměnnou **sledovat** okno, kde můžete také sledovat jeho hodnotu.

   ![Hodnota proměnné během ladění v sadě Visual Studio](media/debugging-variable-value.png)

1. Chcete-li to program dokončen, stiskněte **F5** znovu.

Chcete-li získat další informace o ladění v sadě Visual Studio, najdete v části [ladicího programu prohlídka funkce](../debugger/debugger-feature-tour.md).

## <a name="customize-visual-studio"></a>Přizpůsobení sady Visual Studio

Můžete přizpůsobit integrovaného vývojového prostředí, včetně změny výchozího Barva motivu. Ke změně **tmavý** motivu:

1. Na řádku nabídek zvolte **nástroje** > **možnosti** otevřete **možnosti** dialogové okno.

1. Na **prostředí** > **Obecné** stránka Možnosti, změny **barevný motiv** výběr **tmavý**a potom vyberte **OK**.

   Barva motivu pro celý IDE změny **tmavý**.

   ![VS v tmavý motiv](media/quickstart-personalize-dark-theme.png)

Další informace o další způsoby, můžete přizpůsobit integrovaného vývojového prostředí najdete v tématu [přizpůsobení sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="learn-more"></a>Víc se uč

Chcete vytvořit aplikaci pro Android nebo iOS phone? Co 3D hry nebo aplikace povolenou podporu cloudu? Další informace o těchto a dalších funkcí sady Visual Studio najdete v tématu [funkcí nástroje Visual Studio 2017](../ide/advanced-feature-overview.md).

Pokud jste právě připravení začít nyní kódování, vyberte jednu z rychlý start témata z obsahu, jako například [vytvoření první webové aplikace ASP.NET Core](quickstart-aspnet-core.md).

Můžete se taky podívat na bezplatné sady Visual Studio kurzy k dispozici na [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033).

## <a name="see-also"></a>Viz také:

* [Další funkce sady Visual Studio](../ide/advanced-feature-overview.md)
* [VisualStudio.microsoft.com](https://visualstudio.microsoft.com/vs/)
* [Blog Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/)
* [Soubory ke stažení sady Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)