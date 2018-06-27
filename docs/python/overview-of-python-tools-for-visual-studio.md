---
title: Přehled podpory Python v sadě Visual Studio v systému Windows
description: Souhrn funkcí Python v sadě Visual Studio, takže je nejlepší Python IDE v systému Windows (také označované jako Python Tools pro Visual Studio, PTVS).
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: overview
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 542aedca4aa1cfb472a6cbf1c96c8f46cc8983ec
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2018
ms.locfileid: "36947164"
---
# <a name="work-with-python-in-visual-studio-on-windows"></a>Práce s Python v sadě Visual Studio v systému Windows

Python je oblíbených programovací jazyk, který je spolehlivá, flexibilní, usnadňuje další, bez použití na všech operačních systémech a nepodporuje komunity silné vývojářů a mnoho volné knihovny. Python podporuje všechny způsobů vývoje, včetně webových aplikací, webové služby, aplikace klasické pracovní plochy, skriptování a vědecké výpočty a používá mnoho vysoké školy, vědců, běžné vývojáři a profesionální vývojáře agentem. Další informace o jazyce na [python.org](https://www.python.org) a [Python pro začátečníky](https://www.python.org/about/gettingstarted/).

Visual Studio je výkonný IDE Python v systému Windows. Visual Studio poskytuje [open-source](https://github.com/Microsoft/ptvs) podporu pro jazyk Python prostřednictvím úlohy vývoj Python a vědecké zpracování dat (Visual Studio 2017) a volné Python Tools pro Visual Studio rozšíření (Visual Studio 2015 a dříve).

Python v současné době nepodporuje v sadě Visual Studio pro Mac, ale je k dispozici na Mac a Linux pomocí Visual Studio Code (viz [otázky a odpovědi](#questions-and-answers)).

Abyste mohli začít:

- Postupujte podle [pokyny k instalaci](installing-python-support-in-visual-studio.md) nastavit zatížení Python.
- Seznamte se s možnostmi Python sady Visual Studio prostřednictvím části v tomto článku. Můžete také [přehrát video řady (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121) Úvod do jazyka Python v sadě Visual Studio (celkový počet 22 minut).
- Přejděte prostřednictvím jednoho nebo více Quickstarts k vytvoření projektu. Pokud si nejste jisti, začínat [vytvořit webovou aplikaci s Flask](../ide/quickstart-python.md?context=visualstudio/python/default).
- Postupujte podle [práce s Python v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md) kurz prostředí úplného začátku do konce.

## <a name="support-for-multiple-interpreters"></a>Podpora pro více překladače

Visual Studio **prostředí Python** okno (zobrazené dole v zobrazení široké, rozšířená) poskytuje jednotné místo ke správě všech globální prostředí Python, conda prostředí a virtuální prostředí. Visual Studio automaticky rozpozná instalace jazyka Python ve standardní umístění a umožňuje nakonfigurovat vlastní instalace. S každou prostředí můžete snadno spravovat balíčky, otevřete okno s interaktivní pro prostředí a přístup ke složkám prostředí.

![Rozšířené zobrazení okna prostředí Python](media/environments-expanded-view.png)

Další informace:

- Video (2m 35s): [správu prostředí Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)
- Dokumenty: [prostředí Python Správa](managing-python-environments-in-visual-studio.md)
- Dokumenty: [odkaz na okno prostředí Python](python-environments-window-tab-reference.md)

## <a name="rich-editing-intellisense-and-code-comprehension"></a>Bohaté úpravy, IntelliSense a pochopení kódu

Visual Studio poskytuje prvotřídní editor Python, včetně syntaxe zvýrazňování, automatické doplňování kódu a knihovny, formátování kódu, podpis pomoci, refaktoring linting (viz následující obrázek) a zadejte pomocné parametry. Visual Studio také poskytuje jedinečné funkce, například zobrazení tříd, přejděte na definice, najít všechny odkazy a fragmenty kódu. Přímá integrace s [interaktivních okna](#interactive-window) vám pomůže rychle vytvořit kód Python, který je už uložený v souboru.

![Dokončování kódu pro kód Python v sadě Visual Studio](media/code-editing-completions-simple.png)

Další informace:

- Video (2m 30s): [Python úpravy kódu](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=r2iQH5LWE_4605918567)
- Dokumenty: [Python úpravy kódu](editing-python-code-in-visual-studio.md)
- Dokumenty: [kódu, formátování](formatting-python-code.md)
- Dokumenty: [refaktoring](refactoring-python-code.md)
- Dokumenty: [Linting](linting-python-code.md)
- Funkce dokumentace obecné Visual Studio: [funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)

## <a name="interactive-window"></a>Interaktivní okno

Pro každé prostředí Python, ví, že Visual Studio můžete snadno otevřít stejné interaktivní prostředí (REPL) pro překladač Pythonu přímo v sadě Visual Studio, nikoli pomocí samostatných příkazového řádku. Můžete snadno přepínat mezi prostředími také.

![Interaktivní okno Python v sadě Visual Studio](media/interactive-window.png)

Visual Studio také poskytuje úzkou integraci mezi editoru kódu jazyka Python a interaktivních okna. **Ctrl + Enter** klávesové zkratky pohodlně odešle do okna interaktivní aktuálního řádku v editoru kódu (nebo blok kódu) a pak přesune na další řádek (nebo bloku). **Ctrl + Enter** vám umožní snadno krok prostřednictvím kódu bez nutnosti spuštění ladicího programu. Můžete také odeslat vybraný úsek kódu interaktivní okno s stejné klávesu a snadno vložit do editoru kódu pomocí interaktivních okna. Tyto možnosti společně umožňují pracovní si podrobnosti o segment kódu v okně interaktivní a snadno uložit výsledky do souboru v editoru.

Visual Studio také podporuje IPython/Jupytr v REPL, včetně vložené pozemků, rozhraní .NET a Windows Presentation Foundation (WPF).

Další informace:

- Video (2m 22s: [okno interaktivní Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=gJYKY5LWE_4605918567)
- Dokumenty: [interaktivních okna](python-interactive-repl-in-visual-studio.md)
- Dokumenty: [IPython v sadě Visual Studio](interactive-repl-ipython.md)

## <a name="project-system-and-project-and-item-templates"></a>Systém projektů a šablon projektů a položek

Visual Studio můžete spravovat složitost projektu růstem v čase. Projekt je mnohem víc než strukturu složek: obsahuje k pochopení jak různých souborů se používají a jak se vztahují k sobě navzájem. Visual Studio umožňuje rozlišit kód aplikace, testovací kód, webové stránky, JavaScript, skripty sestavení a tak dále, které povolíte souboru příslušné funkce. Řešení sady Visual Studio navíc umožňuje správu více souvisejících projektů, jako je například Python projektů a rozšíření projektu jazyka C++.

![Řešení sady Visual Studio obsahující projekty Python a C++](media/projects-solution-explorer-two-projects.png)

Šablony projektů a položek automatizovat proces nastavení různé typy projektů a souborů, ušetřit hodně času a kerberosu můžete ve správě komplikované a náchylné podrobnosti. Visual Studio poskytuje šablony pro webové, Azure, vědecké zpracování dat, konzoly a jiné typy projektů, společně s šablon pro soubory, jako jsou třídy Python, testy částí, Azure webové konfigurace, HTML a i aplikace Django.

[![Python šablon projektů a položek v sadě Visual Studio](media/project-and-item-templates.png)](media/project-and-item-templates.png)

Další informace:

- Dokumenty: [Python Správa projektů](managing-python-projects-in-visual-studio.md)
- Dokumenty: [položky templates – referenční informace](python-item-templates.md)
- Dokumenty: [Python šablony projektu](managing-python-projects-in-visual-studio.md#project-templates)
- Dokumenty: [práce s C++ a Python](working-with-c-cpp-python-in-visual-studio.md)
- Funkce dokumentace obecné Visual Studio: [šablon projektů a položek](../ide/creating-project-and-item-templates.md#visual-studio-templates)
- Funkce dokumentace obecné Visual Studio: [řešení a projektů v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)

## <a name="full-featured-debugging"></a>Plnohodnotné ladění

Jedním z Visual Studio síly je jeho výkonný ladicí program. Pro jazyk Python na konkrétní sadě Visual Studio zahrnuje Python/C++ ladění ve smíšeném režimu, vzdálené ladění na systému Linux, vzdáleného ladění na Azure, ladění interaktivních okna a ladění testování částí Python.

![Ladicí program Visual Studio pro jazyk Python zobrazující místní výjimky](media/debugging-exception-popup.png)

Další informace:

- Video: [ladění 3 m 32s Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=Ep5dp5LWE_3805918567)
- Dokumenty: [ladění Python](debugging-python-in-visual-studio.md)
- Dokumenty: [ladění ve smíšeném režimu Python/C++](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- Dokumenty: [vzdáleného ladění na systému Linux](debugging-python-code-on-remote-linux-machines.md)
- Dokumenty: [vzdáleného ladění na Azure](debugging-remote-python-code-on-azure.md)
- Funkce dokumentace obecné Visual Studio: [prohlídka funkce ladicí program Visual Studio](../debugger/debugger-feature-tour.md)

## <a name="profiling-tools-with-comprehensive-reporting"></a>Nástroje pro profilaci s komplexní vytváření sestav

Profilace prozkoumá, jak je právě čas strávený v rámci vaší aplikace. Visual Studio podporuje profilace s na základě CPython překladače a zahrnuje možnost k porovnání výkonu mezi různé profilování spustí.

[![Visual Studio profiler výsledky pro projekt Python](media/profiling-results.png)](media/profiling-results.png)

Další informace:

- Video: [profilace 3 m 00s Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567)
- Dokumenty: [Python nástroje pro profilaci](profiling-python-code-in-visual-studio.md)
- Funkce dokumentace obecné Visual Studio: [profilace prohlídka funkce](../profiling/profiling-feature-tour.md). (Ne všechny funkce profilace aplikace Visual Studio jsou dostupné pro jazyk Python).

## <a name="unit-testing-tools"></a>Nástroje pro testování částí

Zjistit, spustit a správu testů v testovací Průzkumníka Visual Studio a snadno ladění testování částí.

![Ladění jazyka Python testů jednotek v sadě Visual Studio](media/unit-test-debugging.png)

Další informace:

- Video: [testování 2 m 31s Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=hb46k6LWE_405918567)
- Dokumenty: [testování nástroje pro jazyk Python částí](unit-testing-python-in-visual-studio.md)
- Funkce dokumentace obecné Visual Studio: [jednotky Otestujte svůj kód](../test/unit-test-your-code.md).

## <a name="publishing-to-azure-and-azure-sdk-for-python"></a>Publikování do Azure a Azure SDK pro jazyk Python

Visual Studio poskytuje integrovanou podporu pro publikování webových aplikací a cloudové služby Azure. Visual Studio obsahuje nezbytné `web.config` šablon pro obsah dynamických a statických položek. Zatížení Python také obsahuje sadu Azure SDK pro Python, která zjednodušuje využívání služeb Azure z Windows, Mac OS X a Linux aplikace.

![Publikování aplikace Python do Azure v sadě Visual Studio](media/azure-publish-dialog.png)

Další informace:

- Dokumenty: [publikování v Azure](publishing-python-web-applications-to-azure-from-visual-studio.md)
- Dokumenty: [Azure SDK pro Python](azure-sdk-for-python.md)

## <a name="python-training-on-microsoft-virtual-academy"></a>Python školení na webu Microsoft Virtual Academy

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | <ul><li>[Úvod do programování s Pythonem](https://mva.microsoft.com/en-US/training-courses/introduction-to-programming-with-python-8360?l=lqhuMxFz_8904984382)</li><li>[Python Začátečník: Řetězce a funkce](https://mva.microsoft.com/en-US/training-courses/python-beginner-strings-and-functions-18015)</li><li>[Python základy: Seznam a smyčky](https://mva.microsoft.com/en-US/training-courses/python-fundamentals-lists-and-loops-18019)</li><li>[Otázky nejvyšší Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121)</li></ul> |

## <a name="questions-and-answers"></a>Otázky a odpovědi

**Q. Je k dispozici v sadě Visual Studio pro Mac podporu Python?**

A. Není v současné době ale můžete až hlasovat požadavek [UserVoice](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac/suggestions/18670291-python-tools-for-visual-studio-mac). [Visual Studio pro Mac](/visualstudio/mac/) dokumentace identifikuje aktuální typy vývoj, které podporují. Do té doby, Visual Studio Code v systému Windows, Mac a Linux [pracuje s Python prostřednictvím dostupná rozšíření](https://code.visualstudio.com/docs/languages/python).

**Q. Co je můžete použít k vytvoření uživatelského rozhraní s Pythonem?**

A. Hlavní nabídky v této oblasti je [RT projektu](https://www.qt.io/qt-for-application-development/), s vazby pro jazyk Python známé jako [PySide (oficiální vazby)](http://wiki.qt.io/PySide) (také zobrazit [PySide stáhne](https://download.qt.io/official_releases/pyside/.)) a [ PyQt](https://wiki.python.org/moin/PyQt). V současné době podporu jazyka Python v sadě Visual Studio neobsahuje žádné konkrétní nástroje pro vývoj uživatelského rozhraní.

**Q. Můžete vytvořit projekt Python samostatný spustitelný soubor?**

A. Python je obecně interpretovaný jazyk, se kterým je kód spouštět na vyžádání v prostředí vhodný podporující Python například Visual Studio a webovými servery. Visual Studio, sám v současné době neposkytuje způsob, jak vytvořit samostatný spustitelný soubor, což v podstatě znamená programu s embedded překladač Pythonu. Existují však různými prostředky v rámci komunity Python k vytvoření spustitelné soubory, jak je popsáno na [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency). CPython také podporuje probíhá vloženým do nativní aplikace, jak je popsáno v příspěvku na blogu [pomocí CPython li souboru Zip](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/).

## <a name="features-matrix"></a>Matice funkce

Funkce jazyka Python lze nainstalovat v následujících edicích sady Visual Studio, jak je popsáno v [Průvodce instalací](installing-python-support-in-visual-studio.md):

- [Visual Studio 2017 (všechny edice)](https://visualstudio.microsoft.com/vs/)
- Visual Studio 2015 (všechny edice)
- Visual Studio 2013 Community Edition
- Visual Studio 2013 Express pro Web, Update 2 nebo vyšší
- Visual Studio 2013 Express pro plochu, Update 2 nebo vyšší
- Visual Studio 2013 (Pro edice nebo vyšší)
- Visual Studio 2012 (Pro edice nebo vyšší)
- Visual Studio 2010 SP1 (Pro edice nebo vyšší; vyžaduje .NET 4.5)

Jsou k dispozici v sadě Visual Studio 2015 a starší [visualstudio.com/vs/older-downloads/](https://visualstudio.microsoft.com/vs/older-downloads/).

> [!Important]
> Funkce jsou plně podporované a udržovat jenom nejnovější verzi sady Visual Studio. Funkce jsou dostupné v starší verze, ale nejsou aktivně spravovány.

| Podpora v jazyce Python | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Správa více překladače | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automaticky rozpoznat oblíbených překladače | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Přidat vlastní překladače | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Virtuální prostředí | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PIP, snadná instalace | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Projektový systém | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Nový projekt z existujícího kódu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Zobrazit všechny soubory | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Správa zdrojového kódu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Integrace Gitu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004;<sup>1</sup> | &#10007; |
<br/>

| Úpravy | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Zvýraznění syntaxe | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatické dokončování | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Podpis nápovědy | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Rychlé informace | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Objekt prohlížeče nebo třídy zobrazení | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Navigační panel | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Přechod na definici | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Přejděte na | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Najít všechny odkazy | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatické odsazení | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Formátování kódu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Refaktorovat – přejmenovat | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Refaktorovat – extrahování metody | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Refaktorovat – přidat nebo odebrat import | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PyLint | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Interaktivní okno | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Interaktivní okno | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IPython vložené grafů | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Desktop | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Aplikace konzoly a Windows | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| WPF IronPython (pomocí návrháře XAML) | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython Windows Forms | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Web | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Webový projekt Django | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Bottle webového projektu | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Webový projekt flask | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Obecné webového projektu | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Azure | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Nasazení do webové stránky | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004;<sup>2</sup> |
| Nasazení do webové role | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Nasazení do role pracovního procesu | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Spustit v Azure emulátoru | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Vzdálené ladění | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>6</sup> | &#10004;<sup>8</sup> | &#10004;<sup>8</sup> | &#10007; |
| Připojit v Průzkumníku serveru | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>7</sup> | &#10004;<sup>7</sup> | &#10007; | &#10007; |
<br/>

| Django šablony | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Ladění | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatické dokončování | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10004; | &#10004; |
| Automatické dokončování šablon stylů CSS a JavaScript | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10007; | &#10007; |
<br/>

| Ladění | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Ladění | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Ladění bez projektu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Ladění – připojení k úpravám | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Ladění ve smíšeném režimu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Vzdálené ladění (Windows, Mac OS X, Linux) | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Interaktivní okno ladění | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

<a name="matrix-profiling"></a>

| Profilace | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Profilace | &#10004; | &#10004; | &#10004; | &#10007; | &#10007; | &#10004; | &#10004; | &#10004; |
<br/>

| Test | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Průzkumníka testů | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Spuštění testu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Ladění testu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
<br/>

1. Podpora Git pro sadu Visual Studio 2012 je k dispozici ve Visual Studio Tools for Git rozšíření, která je k dispozici na [Galerie sady Visual Studio](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c).

1. Nasazení na web Azure vyžaduje, aby [Azure SDK pro .NET 2.1 - Visual Studio 2010 SP1](http://go.microsoft.com/fwlink/?LinkId=313855). Novější verze sady Visual Studio 2010 se nepodporuje.

1. Podpora pro Azure webovou roli a roli pracovního procesu vyžaduje [Azure SDK pro .NET 2.3 - VS 2012](http://go.microsoft.com/fwlink/?LinkId=323511) nebo novější.

1. Podpora pro Azure webovou roli a roli pracovního procesu vyžaduje [Azure SDK pro .NET 2.3 - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

1. Editor šablon Django ve Visual Studiu 2013 se některé známé problémy, které se vyřeší instalací aktualizace 2.

1. Vyžaduje Windows 8 nebo novější. Visual Studio 2013 Express pro Web nemá připojení do dialogového okna procesu, ale vzdálené ladění webu Azure je stále možné pomocí příkazu připojit ladicí program (Python) v Průzkumníku serveru. Vzdálené ladění vyžaduje [Azure SDK pro .NET 2.3 – Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

1. Vyžaduje Windows 8 nebo novější. Připojit ladicí program (Python) příkaz v Průzkumníku serveru vyžaduje [Azure SDK pro .NET 2.3 – Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

1. Vyžaduje Windows 8 nebo novější.

## <a name="additional-resources"></a>Další zdroje

- [WFastCGI most mezi službou IIS a Python](https://pypi.org/p/wfastcgi) (pypi.org)
- [Volné kurzy Pythonu na webu Microsoft Virtual Academy](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Horní Python dotazy na Microsoft Virtual Academy](https://aka.ms/mva-top-python-questions)
